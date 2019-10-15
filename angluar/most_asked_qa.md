
1- Name the building blocks of Angular.
The Angular application is made using the following: 
 - Modules ( This is used to break the application into the logical pieces of the program code and each piece of code or module is designed to perform a single and unique task.)
 - Component (This is used to bring the modules together.)
 - Template (This is used to define the Views of an Angular application.)
 - Directives
 - Data Binding
 - Services (This component is used to develop the components, which can be used to share in the entire application.)
 - Dependency Injection
 - Routing

2- What is the meaning of component lifecycle in Angular 2 ?
The component lifecycle hooks overview the life cycle sequence and the interfaces. Angular manages the life cycle of a component. Angular creates it, renders it. It can also create and render its children. It also checks when its data-bound properties change. It can even destroy it before removing it from the DOM. The life cycle hook offered by angular provides the visibility into these key life moments and the ability to act when they occur. The components go through an entire set of processes or life cycle right from its initiation to the end of the application.

There are a number of lifecycle hooks which are listed below:–
 - ngOnChanges
 - ngOnInit
 - ngDoCheck
 - ngAfterContentInit
 - ngAfterContentChecked
 - ngAfterViewInit
 - ngAfterViewChecked
 - ngOnDestroy
