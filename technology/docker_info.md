# Docker info

## Механизмы Docker:  
- Платформа Docker — ПО, благодаря которому можно работать с контейнерами.
- Движок Docker — клиент-серверное приложение (CE или Enterprise).
- Клиент Docker — программа, которая позволяет взаимодействовать с демоном Docker посредством CLI.
- Демон Docker — сервер Docker, отвечающий за управление ключевыми механизмами системы.
- Тома Docker — хранилище информации, используемое в контейнерах.
- Реестр Docker — удалённое хранилище образов.
- Хаб Docker — самый крупный реестр Docker, используемый по умолчанию.
- Репозиторий — коллекция образов Docker с одним и тем же именем.

## Масштабирование:  
- Сетевая подсистема Docker — среда, которая позволяет организовывать взаимодействие контейнеров.
- Docker Compose — технология, упрощающая работу с многоконтейнерными приложениями.
- Docker Swarm — средство для управления развёртыванием контейнеров.
- Сервисы Docker — контейнеры в продакшне.

## Команды:  
- Образы. Удаление лишних:  
``` docker rmi $(docker images -q -a) ```   
- Удаление неиспользуемых данных или томов  
    - очистка volumes докера 
        - ```docker volume prune``` 
        - ```system prune -a --volumes ```
    - очистка ресурсов докера 
    ```docker system prune``` 
    - удаление всех volumes от Ильи: 
    ```docker volume rm $(docker volume ls -f dangling=true -q)```

## docker-compose   
- docker-compose up -build -d
- docker-compose down
- docker exec -it <container_name> mc  -- (или bash команду)
- docker-compose restart worker -- Для рестарта одного сервиса


## Java и докер: Запуск сборки образов докеров  
- mvn clean install -P docker_build