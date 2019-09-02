
# OAuth

## Общая информация  
Стандартная работа:  
1. Формируем ссылку для перехода на ресурс. В ссылке учавствуют:
- ID сайта
- response_type = code
- redirect_uri
2. Перенаправляем клиента по сформированной ссылке, он авторизовывается  
3. После успешной авторизации пользователя редиректят к нам на сайт по **rederect_uri**, также они пришлют **code**
4. Получаем **code** на стороне сервера и делаем запрос с **secret_key** для получения **access_token**   
5. В ответ получаем **access_token**, который содержит **user_id**
6. Делаем поиск в БД по **user_id**
7. Если нужно, то запрашиваем дополнительную информацию о пользователе через API


### VK  
_на 08.2019_  
(адрес)[https://vk.com/apps?act=manage]  
У ВК пока работает всё стандартно.
1. Ссылка будет примерно такая:  
```https://oauth.vk.com/authorize```
2. ..
3. ..
4. Делаем запрос на  **access_token**  
```https://oauth.vk.com/access_token```
5. В ответ получим: _access_token_, _user_id_, _expires_in_
6. ..
7. Ссылка для users info:  
```https://api.vk.com/method/users.get```


### Google
_раньше (в 2017) гугл работал как все, сейчас они полностью перешли на JWT_   
(адрес)[console.developers.google.com]  
Полная информация: ```https://accounts.google.com/.well-known/openid-configuration```   
[Гайд от гугла ](https://developers.google.com/identity/protocols/OpenIDConnect?hl=ru#discovery)
1. ```https://accounts.google.com/o/oauth2/auth```
2. ..
3. ..
4. ```https://www.googleapis.com/oauth2/v4/token```
5. В ответ получаем: 
- _access_token_ - старый добрый **access_token** 
- _id_token_ - JWT, который можно расшифровать самостоятельно  
    - Взять ключи открытый ключ ```https://www.googleapis.com/oauth2/v3/certs```
    - Или для debug:  ```https://oauth2.googleapis.com/tokeninfo?id_token=${id_token}```
6. Здесь не будет _user_id_, поэтому его нужно получить либо расшифровав JWT, либо обратившись по адресу:  ```https://openidconnect.googleapis.com/v1/userinfo```, это делается GET запросом, с Bearer авторизацией с _access_token_
7. Ссылка для получения информации о профиле не нужна, так как всё лежит либо в JWT, либо будет ответом в предыдущем пункте

### Facebook
_Facebook также изменил протокол (это у них называется API Graph) и возвращает только access_token_  
(адрес)[https://developers.facebook.com/]  
1. ```https://www.facebook.com/v4.0/dialog/oauth?```
2. ..
3. ..
4. ```https://graph.facebook.com/v4.0/oauth/access_token```
5. В ответ получаем: 
- _access_token_ - старый добрый **access_token** 
- _id_token_ - JWT, который можно расшифровать самостоятельно  
```graph.facebook.com/debug_token?input_token={token-to-inspect}&access_token={app-token-or-admin-token}```
6. Здесь не будет _user_id_, поэтому его нужно получить либо расшифровав JWT, либо обратившись по адресу:  ```https://graph.facebook.com/me?access_token```, это делается GET запросом, с Bearer авторизацией с _access_token_
7. так же как в гугле, ну либо можно юзать API Graph от Facebook


### Instagram
[Вроде тут всё по-старому](https://www.instagram.com/developer/authentication/)


### Github
[тут как у гугла с JWT](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/)  
(адрес)[https://github.com/settings/developers]  
[настройки приложения](https://github.com/settings/developers)

