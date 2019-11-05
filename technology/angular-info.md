# Angular Links  
[How Update Applications](https://update.angular.io/)


## 0 Забавные статьи около Ангуляра
- [**Разговоры про трудоустройство**](https://medium.com/@michelestieven/angular-recurring-problems-i-face-as-a-front-end-consultant-d2a9c1826a3a)
- [**Организация ANGULAR приложения**](https://frontend.consulting/building-an-enterprise-grade-angular-project-structure)
- Что нужно знать по Angular: [habr](https://habr.com/ru/company/alconost/blog/455906/)  [оригинал](https://medium.com/better-programming/19-things-you-need-to-learn-to-become-an-effective-angular-developer-c0ccfa51222a)

### Angular Video
- [**How Angular works - чтоб глубоко понять**](https://youtu.be/S0o-4yc2n-8)
- [**Building with Ivy: Как можно отказаться от Zone.js в пользу реактивщины**](https://youtu.be/rz-rcaGXhGk)

## 1 Angular
- Change Detection Strategy
	- Основы ([Immutable](https://netbasal.com/a-comprehensive-guide-to-angular-onpush-change-detection-strategy-5bac493074a4)) 
	- Глубже
		- [Все, что вам нужно знать об обнаружении изменений в Angular](https://habr.com/post/327004/)
		- [Angular Ivy change detection](https://blog.angularindepth.com/angular-ivy-change-detection-execution-are-you-prepared-ab68d4231f2c)
	- [Максимально глубоко](https://blog.angularindepth.com/these-5-articles-will-make-you-an-angular-change-detection-expert-ed530d28930)
	- [Ошибки при несоблюдении стратегий (на самом деле когда дочерние компоненты меняют родительские)](https://blog.angularindepth.com/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error-e3fd9ce7dbb4)
	- [Стратегия Change-Detection в 2019 году](https://blog.angularindepth.com/how-in-depth-knowledge-of-change-detection-helped-me-improve-applications-performance-daa04cd56ed6)

- Зоны и runOutsideAngular Example (внизу пример)
	- [zone.js без ангуляр](https://blog.thoughtram.io/angular/2016/01/22/understanding-zones.html)
	- [Running code outside Angular’s zone](https://blog.thoughtram.io/angular/2016/02/01/zones-in-angular-2.html#ngzone-in-angular)

- ng-content, ViewChildren, ContentChildren
	- [Understanding ViewChildren, ContentChildren, and QueryList](https://netbasal.com/understanding-viewchildren-contentchildren-and-querylist-in-angular-896b0c689f6e)
	- [Подробнее](https://medium.com/@tkssharma/understanding-viewchildren-viewchild-contentchildren-and-contentchild-b16c9e0358e)

- Angular Events
	- [написание своих обработчиков эвентов](https://habr.com/ru/company/tinkoff/blog/429692/)

- LifeCycles
	- [**OnInit**](https://ultimatecourses.com/blog/exploring-angular-lifecycle-hooks-oninit)

- Работа с Validators и Формами и NG-Group
	- [Custom form control](https://blog.thoughtram.io/angular/2016/07/27/custom-form-controls-in-angular-2.html)
	- [Добавление валидаторов к компоненту внутри директивы](https://blog.angularindepth.com/a-little-trick-with-angular-forms-and-directives-137e2c53f25)
	
- Data Binding
	- [Двустороннее связывание Angular](https://habr.com/ru/post/453696/)
	- [Understanding Data Binding](https://blog.bitsrc.io/data-binding-in-angular-cbc433481cec)
	- **ngModelGroup** в компонентах и **ControlValueAccessor**:
		- [ ngModelGroup ]="name", а в компоненте: viewProviders: [{ provide: ControlContainer, useExisting: NgForm }],
		- [**ControlValueAccessor**](https://habr.com/ru/company/tinkoff/blog/443714/)

- Pipes and Async Pipes
	- [**Async Pipe Deep**](https://medium.com/better-programming/angular-rxjs-async-pipe-deep-dive-2510b56f793a)
	- [**Async Pipe Deep Dive** - почему это плохо и как оно в реальности работает](https://medium.com/@erxk_verduin/angular-rxjs-async-pipe-deep-dive-2510b56f793a)

- angular Progressive Web Application (PWA)
	- [Общее](https://habr.com/ru/post/303626/)
	- [**PRPL pattern**](https://itnext.io/the-prpl-pattern-for-progressive-web-applications-using-angular-6-f7237b7dc2a7)
	- [Build PWA](https://blog.angularindepth.com/build-a-progressive-web-app-with-angular-bf7d66744020)
	- [**Modern Web App**](https://habr.com/ru/post/432368/)
	- [**PWA with vanilla-javascript**](https://levelup.gitconnected.com/build-a-pwa-using-only-vanilla-javascript-bdf1eee6f37a)

- Внедрение зависимостей  
	- [Внедрение зависимостей](https://habr.com/ru/post/429342/)
	- [Как можно внедрить Enviroment в разные части проекта](https://codeburst.io/angular-dependency-injection-tips-ddb24b8244be)

- Reactive Forms  
	- [**Say Goodbye to Angular Template-Driven**](https://netbasal.com/why-its-time-to-say-goodbye-to-angular-template-driven-forms-350c11d004b)
	- [**Реактивные формы с компонентами**](https://itnext.io/partial-reactive-form-with-angular-components-443ca06d8419)
		- [Понятный пример](https://stackblitz.com/edit/monolithic-reactive-form?file=app%2Fapp.component.html)

- Lazy Loading  
	- [**Как работает LazyLoading в WebPack**](https://ultimatecourses.com/blog/lazy-loading-angular-code-splitting-webpack)
	- [**Router Updates in 7.1 + порядок гвардов**](https://blog.angularindepth.com/new-in-angular-v7-1-updates-to-the-router-fd67d526ad05)
	- [**Lazy Load Non-Routable Modules**](https://netbasal.com/the-need-for-speed-lazy-load-non-routable-modules-in-angular-30c8f1c33093)

- Локализация
	- [Мультиязычные приложения в Angular](https://habr.com/ru/post/446402/)
	- [Интернационализация (i18n) в Angular 2](https://habr.com/ru/post/323180/)
	- [**Пример с понятными настройками билдинга**](https://alligator.io/angular/internationalization/)

- Новый движок рендера Ivy 
	- [**Вводная**](https://blog.angularindepth.com/all-you-need-to-know-about-ivy-the-new-angular-engine-9cde471f42cf)
	- [**Асинхронные модули и Компоненты для Ivy**](https://blog.angularindepth.com/asynchronous-modules-and-components-in-angular-ivy-1c1d79d45bd3)

- Angular 6
	- Library for Angular
		- [Как создавать библиотеки](https://medium.com/@tomsu/how-to-build-a-library-for-angular-apps-4f9b38b0ed11)

	- WorkSpaces
		- [Test-Drive](https://medium.com/@angularlicious/angular-6-workspace-test-drive-cfe24bbceeb3)

	- **CLI Builders**  
		- [Оригинал](https://blog.angular.io/introducing-cli-builders-d012d4489f1b)  [Перевод](https://habr.com/ru/post/450746/)

- Angular 8
	- [Обзор](https://medium.com/webbdev/angular-4c42d86eaa62)
	- [Что нового в Angular 8](https://habr.com/ru/post/455493/)
	- [Миграция до 8 ангуляра](https://www.techiediaries.com/updating-angular-cli-projects/)


## 2 Angular Optimization 
- Общее
	- [Простые советы](https://www.telerik.com/blogs/tips-for-optimizing-your-angular-application)
	- [Глубокие советы](https://m.habr.com/ru/company/ruvds/blog/425661/)  [Оригинал](https://www.freecodecamp.org/news/best-practices-for-a-clean-and-performant-angular-application-288e7b39eb6f/)

- Когда глючит ngFor:
	- [trackBy - оптимизация](https://netbasal.com/angular-2-improve-performance-with-trackby-cc147b5104e5)

- [Тут всякие приёмчики](https://www.newline.co/@kievsash/mastering-angular-8:-five-things-that-are-good-to-know-to-save-your-time.--6302e8aa)
	- Как делать редиректы между компонентами без потери QueryParams
	- Как делать редирект на такой же роут (обновить или реаинициалилизировать роут - похоже на костыль)
	- Почему нельзя импортировать важные модули много раз
	- Как подсветить только часть нужного текста в пару строк  -  ::ng-deep CSS директива

		

## 3 RxJS
- retryWhen and pipe:
	- [**Understanding Lettable Operators**](https://blog.angularindepth.com/rxjs-understanding-lettable-operators-fe74dda186d3)
	- [**retryWhen**](https://www.learnrxjs.io/operators/error_handling/retrywhen.html)
- takeUntill:
	- [Очень простой пример](https://alligator.io/angular/takeuntil-rxjs-unsubscribe/)
	- [Закрытие пайпов через until](https://medium.com/@benlesh/rxjs-dont-unsubscribe-6753ed4fda87)

- concatMap, mergeMap, switchMap (для работы с множеством одинаковых запросов):
	- [concatMap vs mergeMap vs forkJoin](https://blog.angularindepth.com/practical-rxjs-in-the-wild-requests-with-concatmap-vs-mergemap-vs-forkjoin-11e5b2efe293)
	- [mergeMap and switchMap](https://netbasal.com/understanding-mergemap-and-switchmap-in-rxjs-13cf9c57c885)

- [просто общая инфа по Observable](https://habr.com/post/337512/) 
- [**Never think of RxJs Subscriptions again**](https://blog.angularindepth.com/having-fun-with-angular-and-typescript-transformers-2c2296845c56)
	- Тут делают плагин для вебпака, который в каждый subscribe добавить unsubscribe - очень глубокое понимание работы


## 4 NGRX:  
- [Реактивные приложения на Angular/NGRX. Часть 2. Store](https://medium.com/@demyanyuk/%D1%80%D0%B5%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BD%D0%B0-angular-ngrx-%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-1412bc9adf17)
- [Реактивные приложения на Angular/NGRX. Часть 3. Effects.](https://medium.com/@demyanyuk/%D1%80%D0%B5%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BD%D0%B0-angular-ngrx-%D1%87%D0%B0%D1%81%D1%82%D1%8C-3-effects-6f4b34dfa289)
- [NgRx Store: архитектура для Angular приложений](https://golosay.net/ngrx-store-architecture/)

- [Redux Store Example](https://www.telerik.com/blogs/building-a-food-store-using-redux-and-angular)
- [Redux, Angular Style: ngrx/store](https://blog.usejournal.com/redux-angular-style-ngrx-store-b2876280708e)


## Angular Animation
- [**Angular Animation**](https://medium.com/@GrandSchtroumpf/a-journey-into-angular-animation-f3360739c705)
- [Простой пример анимации через Canvas](https://blog.angularindepth.com/how-to-get-started-with-canvas-animations-in-angular-2f797257e5b4)


## Angular-Examples
- [Создание адаптивного хеадера с менюшкой + анимация](https://medium.com/fafnur/%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-%D0%B2%D0%B5%D1%80%D1%81%D1%82%D0%BA%D0%B8-%D0%B2-angular-c-redux-%D0%B8-nx-2da5e0b8e3e8)
- [Создание красивых и понятных сообщений об ошибках](https://netbasal.com/make-your-angular-forms-error-messages-magically-appear-1e32350b7fa5)
- [Взаимодействие между компонентами Angular с использованием RxJS](https://habr.com/ru/post/471100/)


## 6 Angular Material (Angular Components)
- [typography](https://material.angular.io/guide/typography)
- [components](https://material.angular.io/components/categories)
- [icons](https://material.io/tools/icons/?icon=check&style=baseline)  


## 7 Multi Apps
- [**Bootstrapping multiple Angular 2 applications on the same page**](https://blog.sstorie.com/bootstrapping-multiple-angular-2-applications-on-the-same-page/)
	- [github](https://github.com/sstorie/experiments/blob/master/angular2-multiple-applications/index.html)
- [**Multiapps on ONE project**](https://github.com/angular/angular-cli/wiki/stories-multiple-apps)

## Angular - библиотеки в помощь
- [обзор](https://www.telerik.com/blogs/17-angular-libraries-you-should-know-about)

## Angular and Bit
- [**Sharing Components with Angular and Bit**](https://blog.bitsrc.io/sharing-components-with-angular-and-bit-b68896806c18)
