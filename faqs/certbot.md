# Certbot for VDS

## Установка
```bash
$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository universe
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install certbot 
```

## Как должно работать
Получение сертификата:  
webroot создаёт в папке webroot-path специальный файл и потом должен его же получить  
поэтому нужна именно такая настройка. вроде сертификаты таким образом работают. узнаем через месяц (11.06.2019)
sudo certbot certonly --webroot --webroot-path ~/projects/nginx/src/ -d menkent.dev -d www.menkent.dev 
sudo certbot certonly --webroot --webroot-path ~/projects/nginx/src/ -d menkent.dev -d www.menkent.dev 

сертификаты окажутся тут: /etc/letsencrypt/live/menkent.dev/


## Получить сертификаты на все поддомены (wildcard)
- https://itc-life.ru/poluchaem-letsencrypt-wildcard-sertifikat/
- https://wiki.yola.ru/letsencrypt:wildcard 



### Алгоритм работы для WildCard
1. Вызываем  
```sudo certbot certonly --manual -d *.menkent.dev -d menkent.dev --server https://acme-v02.api.letsencrypt.org/directory```
2. Заходим в настройки хостинга и создаём там TXT Record  
поддомен **_acme-challenge**   а значение такое, как попросит сам certbot
3. Автоматическое обновление пока не работает, поэтому вызываем так:  
```bash
# обновление сертификата через ТТХ запись
sudo certbot certonly --manual --preferred-challenges dns --server https://acme-v02.api.letsencrypt.org/directory -d *.menkent.dev -d menkent.dev

# проверка, что запись применилась (осторожно, оно кешируется)
nslookup -type=TXT _acme-challenge.menkent.dev
```



## Commands
### авто-обновление 
1. пока не работает. Есть вариант такой:  
https://developerinsider.co/how-to-create-and-auto-renew-lets-encrypt-wildcard-certificate/  
или такой:  https://medium.com/@cubxi/add-wildcard-lets-encrypt-certifications-with-namecheap-6a466df0886f  
ещё есть такая статья  https://blog.bryanroessler.com/2019-02-09-automatic-certbot-namecheap-acme-dns/  

но здесь нужно скачивать что-то левое, а дальше должно работать так:  
```./certbot-auto certonly --manual -d *.menkent.dev -d menkent.dev --server https://acme-v02.api.letsencrypt.org/directory```

2. НЕ ЗАБЫТЬ ПОСЛЕ АВТО-ОБНОВЛЕНИЯ СЕРТИФИКАТОВ (hook) - [РЕСТАРТ NGINX](https://www.guyrutenberg.com/2017/01/01/lets-encrypt-reload-nginx-after-renewing-certificates/)  
положил хук на рестарт docker контейнера с nginx на обновление. Посмотрим что получится
3. Создание файла-хука:   
```bash
touch reload-nginx.sh     # создать файл 
chmod +x reload-nginx.sh  # сделать файл исполняемым
```
4. Содержимое файла-хука
```bash
#! /bin/sh
docker restart nginx -t=60
```


### Вариант применения сертификатов для всех серверов (vhost) в nginx
```config
server {
  listen              127.0.0.1:443 default_server ssl;
  server_name         _;
  ssl_certificate     /etc/ssl/wildcard.cer;
  ssl_certificate_key /etc/ssl/wildcard.key;
}

server {
  listen      127.0.0.1:443;
  server_name a.example.com;
  root        /data/httpd/a.example.com;
}

server {
  listen      127.0.0.1:443;
  server_name b.example.com;
  root        /data/httpd/b.example.com;
}
```



