
# RabbitMQ

## DockerHUB  
[link](https://hub.docker.com/_/rabbitmq/)  
- database dir   : /var/lib/rabbitmq/mnesia/rabbit@my-rabbit
- docker-compose example  
```yaml
rabbitmq:
  image: "rabbitmq:3.7.15-management"
  hostname: "rabbitmq"
  environment:
    RABBITMQ_ERLANG_COOKIE: "SWQOKODSQALRPCLNMEQG"
    RABBITMQ_DEFAULT_USER: "rabbitmq"
    RABBITMQ_DEFAULT_PASS: "rabbitmq"
    RABBITMQ_DEFAULT_VHOST: "/"
  ports:
    - "15672:15672"
    - "5672:5672"
  labels:
    NAME: "rabbitmq"
  volumes:
    - "./enabled_plugins:/etc/rabbitmq/enabled_plugins"
```

## Tutorials
- [хорошая хабр статья](https://habr.com/ru/post/149694/)  
  - соединение: 
  ```py
    connection = pika.BlockingConnection(pika.ConnectionParameters(host='localhost'))
    channel = connection.channel()
  ```
  - объявление очереди, сделать во всех программах 
  ```channel.queue_declare(queue='hello')```
  - отправка:  
  ```channel.basic_publish(exchange='', routing_key='hello',  body='Hello World!')```
  - получение через callback  (no_ack - автоматическое подтверждение)
  ```channel.basic_consume(callback,  queue='hello',  no_ack=False) ```
- [статья, описывающая работу с подтверждением получения сообщений](https://habr.com/ru/post/150134/)
  - нужно подтверждать сообщение  ```ch.basic_ack(delivery_tag = method.delivery_tag)```
  - создание устойчивой очереди: ```queue_declare(queue='hello', durable=True)```
  - создание устойчивых сообщений: ```properties=pika.BasicProperties(delivery_mode=2)```
  - максимум сообщений на одного подписчика: ```channel.basic_qos(prefetch_count=1)```

- AMQP протокол. Часто-используемые поля
  - delivery_mode  (устойчивость сообщения = 2)
  - content_type (например, тип сообщения = "application/json")
  - reply_to - обычно используется для указания очереди результатов;
  - correlation_id: свойство используется для сопоставления RPC ответов с запросами.

- Exchange Points
  - fanout - https://habr.com/ru/post/200870/   (все очереди)
  - direct - https://habr.com/ru/post/201096/   (только совпадающие по ключам)
  - topic - https://habr.com/ru/post/201178/   (тематика с * или # - интересно весьма сделано)

- RPC пример - https://habr.com/ru/post/236221/ 


