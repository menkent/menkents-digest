# Angular Links

## 0 Забавные статьи около Ангуляра
- [**Разговоры про трудоустройство**](https://medium.com/@michelestieven/angular-recurring-problems-i-face-as-a-front-end-consultant-d2a9c1826a3a)
- [**Организация ANGULAR приложения**](https://frontend.consulting/building-an-enterprise-grade-angular-project-structure)


## 1 Angular Change Detection Strategy
- Основы (Immutable ! ) https://netbasal.com/a-comprehensive-guide-to-angular-onpush-change-detection-strategy-5bac493074a4
- Глубже
	- https://habr.com/post/327004/
	- https://blog.angularindepth.com/angular-ivy-change-detection-execution-are-you-prepared-ab68d4231f2c
- Максимально глубоко: https://blog.angularindepth.com/these-5-articles-will-make-you-an-angular-change-detection-expert-ed530d28930

- Зоны и runOutsideAngular Example (внизу пример)
	- https://blog.thoughtram.io/angular/2016/01/22/understanding-zones.html   (zone.js без ангуляр)
	- https://blog.thoughtram.io/angular/2016/02/01/zones-in-angular-2.html#ngzone-in-angular

- ng-content
	- https://netbasal.com/understanding-viewchildren-contentchildren-and-querylist-in-angular-896b0c689f6e
	- https://medium.com/@tkssharma/understanding-viewchildren-viewchild-contentchildren-and-contentchild-b16c9e0358e

- Ошибки при несоблюдении стратегий (на самом деле когда дочерние компоненты меняют родительские)  
	- https://blog.angularindepth.com/everything-you-need-to-know-about-the-expressionchangedafterithasbeencheckederror-error-e3fd9ce7dbb4

- Работа с эвентами в ангуляр - написание своих обработчиков эвентов
	- https://habr.com/ru/company/tinkoff/blog/429692/

- LifeCycles
	- [**OnInit**](https://ultimatecourses.com/blog/exploring-angular-lifecycle-hooks-oninit)

- Работа с Validators и Формами и NG-Group
	- https://blog.thoughtram.io/angular/2016/07/27/custom-form-controls-in-angular-2.html
	
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
	- https://itnext.io/the-prpl-pattern-for-progressive-web-applications-using-angular-6-f7237b7dc2a7
	- https://blog.angularindepth.com/build-a-progressive-web-app-with-angular-bf7d66744020
	- [**Modern Web App**](https://habr.com/ru/post/432368/)

- [Внедрение зависимостей](https://habr.com/ru/post/429342/)

- Reactive Forms  
	- [**Say Goodbye to Angular Template-Driven**](https://netbasal.com/why-its-time-to-say-goodbye-to-angular-template-driven-forms-350c11d004b)

- Lazy Loading  
	- [**Как работает LazyLoading в WebPack **](https://ultimatecourses.com/blog/lazy-loading-angular-code-splitting-webpack)
	- [**Router Updates in 7.1 + порядок гвардов**](https://blog.angularindepth.com/new-in-angular-v7-1-updates-to-the-router-fd67d526ad05)

- Локализация
	- [Мультиязычные приложения в Angular](https://habr.com/ru/post/446402/)


- Angular 6
	- Library for Angular
		- https://medium.com/@tomsu/how-to-build-a-library-for-angular-apps-4f9b38b0ed11  

	- WorkSpaces
		- https://medium.com/@angularlicious/angular-6-workspace-test-drive-cfe24bbceeb3  

	- **CLI Builders**  
		- https://blog.angular.io/introducing-cli-builders-d012d4489f1b
		- https://habr.com/ru/post/450746/

- Angular 8
	- [Обзор](https://medium.com/webbdev/angular-4c42d86eaa62)
	- [Что нового в Angular 8](https://habr.com/ru/post/455493/)



## 2 Angular Optimization 
- Основы
	- https://m.habr.com/ru/company/ruvds/blog/425661/
	- https://webformyself.com/stimulyaciya-proizvoditelnosti-vashego-prilozheniya-na-frejmvorke-angular-4/
	- https://www.telerik.com/blogs/tips-for-optimizing-your-angular-application

- Когда глючит ngFor  (trackBy - оптимизация)
	- https://netbasal.com/angular-2-improve-performance-with-trackby-cc147b5104e5
		


## 3 RxJS
- retryWhen and pipe:
	- https://blog.angularindepth.com/rxjs-understanding-lettable-operators-fe74dda186d3 
	- https://www.learnrxjs.io/operators/error_handling/retrywhen.html
- takeUntill:
	- https://alligator.io/angular/takeuntil-rxjs-unsubscribe/
	- закрытие пайпов через until: [link](https://medium.com/@benlesh/rxjs-dont-unsubscribe-6753ed4fda87)

- concatMap, mergeMap, switchMap (для работы с множеством одинаковых запросов):
	- https://blog.angularindepth.com/practical-rxjs-in-the-wild-requests-with-concatmap-vs-mergemap-vs-forkjoin-11e5b2efe293
	- https://netbasal.com/understanding-mergemap-and-switchmap-in-rxjs-13cf9c57c885

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

## 6 Angular Material (Angular Components)
- https://material.angular.io/guide/typography  
- https://material.angular.io/components/categories  
- https://material.io/tools/icons/?icon=check&style=baseline  


## Angular - библиотеки в помощь
- [обзор](https://www.telerik.com/blogs/17-angular-libraries-you-should-know-about)
