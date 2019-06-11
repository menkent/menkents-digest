# dante server 

## docker hub
- https://hub.docker.com/r/vimagick/dante/

## запуск делаем так: 
в докер-компоузе вызываем свой же файл: 
```command: bash ./user_add.sh```

который выглядит так:
```bash
#!/bin/bash
useradd user1
echo user1:12345 | chpasswd
sockd
```
