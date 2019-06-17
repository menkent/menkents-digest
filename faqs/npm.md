
# NPM and NODE:

## Установка и обновление:
### Windows:  
- Установка - просто скачиваем с сайта и ставим
- Обновление - делаем следующее:
	- Обновление для NODE - скачиваем с сайта
	- Обновление для NPM без затрагивания NODE
		- Заходим в CMD от администратора
		- идём в Program Files/nodejs и выполняем там: 
		```bash 
		npm install -g npm-windows-upgrade
		npm-windows-upgrade
		```
### Ubuntu:
- Установка:
- Обновление  
	```bash
	sudo npm cache clean -f
	sudo npm install -g n
	sudo n stable   # Стабильная версия
	sudo n latest   # Последняя версия
	```