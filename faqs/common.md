
# Общие знания по VDS и Domain:

## Настройка DNS для моего хостинга:
- [Сама настройка](https://www.namecheap.com/support/knowledgebase/article.aspx/319/2237/how-can-i-set-up-an-a-address-record-for-my-domain)  
- Нам нужна только A-Record - именно здесь мы указываем IP  
- CNAME - для поддоменов
- www.menkent.dev - можно указать, оно будет считать как поддоменов
- TXT Record для получения сертификатов с ручной проверкой (для *.domain)

## VDS
### Создание пользователя
- https://timeweb.com/ru/community/articles/instrukciya-po-nastroyke-vds-bazovaya-konfiguraciya-i-rabota-s-lemp-1
- ```adduser username```
		
### Добавление ssh ключей для беспарольного доступа
https://firstvds.ru/technology/dobavit-ssh-klyuch
		 
### Управление SSH
```bash
nano /etc/ssh/sshd_config
PasswordAuthentication no
Port 22 -> 50132
```

## Docker - установить, настроить пользователей и тд - в отдельных файлах
- Установка Docker и Docker-Compose  (+ работа с пользователями)
- https://www.digitalocean.com/community/tutorials/docker-ubuntu-18-04-1-ru
- https://docs.docker.com/compose/install/

## Nginx, SSH и Certbot
-  Основное описано в файле по certbot, но сюда добавлю инфу по настроке nginx с рекомендациями по зправильной донастройке ssh
	- https://habr.com/ru/post/325230/
	- https://gist.github.com/nrollr/9a39bb636a820fb97eec2ed85e473d38
	- https://mozilla.github.io/server-side-tls/ssl-config-generator/
		
- [Один сертификат для всех поддоменов](https://serverfault.com/questions/548938/multiple-ssl-vhosts-using-wildcard-certificate-in-nginx)  		
- Так как мы используем docker-hub/nginx, то у него есть свои особенности с настройками:  
	- все настройки импортируются этой строкой: 
		- ```include /etc/nginx/conf.d/*.conf;```
	- Значит мы делаем следующее
		- Общие настройки кладём в *.conf файл и пусть он импортируется как обычно
			```conf
			volumes:
				- ./config/nginx.conf:/etc/nginx/conf.d/my-start.conf
			```
		- Дополнительные настройки поддоменов кладём в подпапку и уже их импортируем в нашем файле
			
## Dante - proxy server
- Будем также использовать докер-контейнер:
	- https://hub.docker.com/r/vimagick/dante/
	- https://typaknote.ru/private-socks5-server/
- Проблема: создать внутри контейнера отдельного пользователя, так как выполнить команды с compose сложно
	- вариант заменить Dockerfile: https://github.com/Medic84/dante-compose
	- вариант выполнить команды из зависимого docker-compose файла: https://stackoverflow.com/questions/45774221/how-to-run-docker-exec-on-a-docker-compose-yml
- Настройки сервера: https://www.proxyrack.com/how-to-setup-a-socks5-proxy-server-using-dante/
	


## openvpn - vpn для локальной сети и будет работать даже с win-10 
- https://habr.com/ru/post/354632/
	
	