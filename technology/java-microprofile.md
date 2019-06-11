# Информация о микропрофилях JAVA  

## Просто информация:  
- [пример](https://www.codeflow.site/ru/article/eclipse-microprofile)
- для работы с другими адресами, кроме локалхоста:  
```server.xml -> httpEndpoint -> host="*"```
- Типы аннотаций:  
	- @RequestScoped -  на каждый запрос объект класса будет пересоздаваться 
	- @ApplicationScoped - на весь Application - единый объект (Для сервисов подходит)
	- @Consumes - формат данных, который будет принимать EndPoint
	- @Produces - формат данных, который будет отдавать EndPoint
	
## Интересная инфа по микропрофилю:  
[тыц](https://openliberty.io/blog/2018/09/19/get-more-metrics-microprofile20.html)


## HIBERNATE в JAVA
- https://www.baeldung.com/java-json-binding-api
- пакетные вставки  
	- https://habr.com/ru/post/269029/  
	- https://www.tutorialspoint.com/hibernate/hibernate_batch_processing.htm  
- Для работы хибернейта нужно использовать HikaryCP в качестве conection pool


## SWAGGER/OpenAPI
- https://www.javacodegeeks.com/2018/08/swagger-ui-microprofile-openapi.html
- https://swagger.io/docs/specification/describing-parameters/
- https://github.com/swagger-api/swagger-core/wiki/Swagger-2.X---Annotations#operation-annotations  


## Метрики:
- Правильная статья по метрикам: [link](https://dzone.com/articles/get-more-metrics-from-your-apps-with-microprofile)
- Статья для использования метрик: [link](https://www.tomitribe.com/blog/getting-started-with-microprofile-metrics/)
- Для использования Histogram-метрик нужно:   
```java
@Inject
@RegistryType(type=MetricRegistry.Type.APPLICATION)
MetricRegistry metricRegistry; 
```
- По-умолчанию работает так: http://localhost:8080/metrics/application/<MetricName>


## JWT:
- как работает JWT:	
	- [статья-1](https://ru.wikipedia.org/wiki/JSON_Web_Token)
	- [статья-2 + обсуждения](https://gist.github.com/zmts/802dc9c3510d79fd40f9dc38a12bccfc)
- [библиотека с примерами](https://connect2id.com/products/nimbus-jose-jwt)
- [Как должен выглядеть JWT](https://www.eclipse.org/community/eclipse_newsletter/2017/september/article2.php)  
- Генерация самого JWT 
- нужно правильно настраивать mpJwt для расшифровки  
	- [документация для OpenLiberty](https://www.ibm.com/support/knowledgecenter/en/was_beta_liberty/com.ibm.websphere.wlp.nd.multiplatform.doc/ae/twlp_sec_json.html)
	- [документация для OpenLiberty для JWT](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_liberty/com.ibm.websphere.wlp.doc/ae/twlp_sec_config_jwt_sso.html)
- [правильная генерация ключей](https://en.wikibooks.org/wiki/Cryptography/Generate_a_keypair_using_OpenSSL)
- Правильный запуск с ключами:
	- ``` java -jar <name>/target/<name>.jar -Dmp.jwt.verify.publickey.location=/public.pem ```
	- ``` java -jar compliance-ms/target/compliance-ms.jar -Dmp.jwt.verify.publickey.location=/public.pem ```
- Алгоритм создания JWT прост:  
	1. Формируем список групп и других данных в JSON объекте (JSONObject)
	2. Заполняем Claims для JWT - это такой класс, куда мы обязательно поместим: 
		- iss - кто выдал token
		- aud - на какой ресурс
		- groups - для каких групп 
		- sub - и подгрупп 
		- iat - в какое время
		- exp - на какое время
		- и другие поля по желанию 
	3. Оборачиваем в JWTClaimsSet
	4. Генерируем JWT
	```java
		JWSHeader headerS = new JWSHeader.Builder(RS256).keyID("/private.pem").type(JWT).build();
		SignedJWT signedJWT = new SignedJWT(headerS, claimsSet);
		PrivateKey key = readPrivateKey("/private.pem");
		RSASSASigner signer = new RSASSASigner(key);
		signedJWT.sign(signer);
		String s = signedJWT.serialize();
	```
	5. readPrivateKey - функция, которая формирует приватный ключ:  
	```java
		InputStream contentIS = MSApplication.class.getResourceAsStream(resourceName);
        byte[] tmp = new byte[2048];
        int length = contentIS.read(tmp);
        String pemEncoded = new String(tmp, 0, length)
                .replaceAll("-----BEGIN (.*)-----", "")
                .replaceAll("-----END (.*)----", "")
                .replaceAll("\r\n", "")
                .replaceAll("\n", "")
                .trim();
        byte[] pkcs8EncodedBytes = Base64.getDecoder().decode(pemEncoded);
        PKCS8EncodedKeySpec keySpec = new PKCS8EncodedKeySpec(pkcs8EncodedBytes);
        KeyFactory kf = KeyFactory.getInstance("RSA");
        PrivateKey pk = kf.generatePrivate(keySpec);
        return pk;
	```

