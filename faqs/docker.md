
# Установка Docker и Docker-Compose  (+ работа с пользователями)
- https://www.digitalocean.com/community/tutorials/docker-ubuntu-18-04-1-ru
- https://docs.docker.com/compose/install/
- https://docs.docker.com/compose/compose-file/

## Частые команды для работы с докером  
- ```docker-compose up --build -d```
- ```docker-compose build --no-cache --force-rm && docker-compose up -d```
- ```docker-compose down```
- ```docker-compose logs ```
- ```docker stats```
- ```docker ps```
- ```docker exec -it nginx /bin/sh```
- ```docker rmi $(docker images -a -q)```
	
	
	
	