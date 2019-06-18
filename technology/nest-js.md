# [NestJS](https://nestjs.com/)  
NestJS - тот самый, настоящий бэкенд на nodejs  
[docs](https://docs.nestjs.com/)  

## Статьи  
- [Вводная статья с хабра](https://habr.com/ru/post/439434/)

## С чего начать  
- [Хороший пример из чата](https://github.com/ZackFox/face-list-nestserver)
### Установка
### Добавление passport-js и jwt



## Полезности, которые могут пригодиться  
- Как сохранить с формы файл и поля одним запросом  
```ts 
    @UseInterceptors(FileInterceptor('file'))
    @ApiConsumes('multipart/form-data')
    @ApiImplicitFile({ name: 'file', required: true })
    async createVectorLayer(@Body() params: any, @UploadedFile() files) {
```