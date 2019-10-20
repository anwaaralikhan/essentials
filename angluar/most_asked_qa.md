
- Name the building blocks of Angular
The Angular application is made using the following: 
 * Modules ( This is used to break the application into the logical pieces of the program code and each piece of code or module is designed to perform a single and unique task.)
 - Component (This is used to bring the modules together.)
 - Template (This is used to define the Views of an Angular application.)
 - Directives
 - Data Binding
 - Services (This component is used to develop the components, which can be used to share in the entire application.)
 Services help us in not repeating the code. With the creation of services, we can use the same code from different components. Here is the command to create a service in angular, ng g service User (a UserService is created when this command is used). 
 
 - Dependency Injection
 - Routing

2- What is the meaning of component lifecycle in Angular 2 ?
The component lifecycle hooks overview the life cycle sequence and the interfaces. Angular manages the life cycle of a component. Angular creates it, renders it. It can also create and render its children. It also checks when its data-bound properties change. It can even destroy it before removing it from the DOM. The life cycle hook offered by angular provides the visibility into these key life moments and the ability to act when they occur. The components go through an entire set of processes or life cycle right from its initiation to the end of the application.

There are a number of lifecycle hooks which are listed below:–
 - ngOnChanges
 - ngOnInit (It initializes the component content)
 - ngDoCheck
 - ngAfterContentInit
 - ngAfterContentChecked (It checks the binding of the external content.)
 - ngAfterViewInit (It creates the component view.)
 - ngAfterViewChecked (It checks the bindings of the component’s view)
 - ngOnDestroy
 
 
 
 ngOnChanges - This is called when data changes in your application that affects this component specifically
ngOnInit - This is called when the component initializes for the first time (i.e. it's only called once)
ngOnDestroy - This is called when the component is about to be destroyed (i.e. removed from the page)
 
 
 Here are the lifecycle hooks available, in the order in which they are invoked:

ngOnChanges: Called every time a data-bound input property changes. It’s called a first time before the ngOnInit hook. The hook receives a SimpleChanges object that contains the previous and current values for the data-bound inputs properties. This hook gets called often, so it’s a good idea to limit the amount of processing it does.
ngOnInit: Called once upon initialization of the component.
ngDoCheck: Use this hook instead of ngOnChanges for changes that Angular doesn’t detect. It gets called at every change detection cycle, so keeping what it does to a minimum is important for performance.
ngAfterContentInit: Called after content is projected in the component.
ngAfterContentChecked: Called after the projected content is checked.
ngAfterViewInit: Called after a component’s view or child view is initialized.
ngAfterViewChecked: Called after a component’s view or child view is checked.
ngOnDestroy: Called once when the component is destroyed and a good hook to use to cleanup and unsubscribe from observables.



 
Differentiate between Components and Directives in Angular 5.
Components break up the application into smaller parts; whereas, Directives add behavior to an existing DOM element. 

What is the use of @Input and @Output? 
When it comes to the communication of Angular Components, which are in Parent-Child Relationship; we use @Input in Child Component when we are passing data from Parent to Child Component and @Output is used in Child Component to receive an event from Child to Parent Component. 


In how many ways the Data Binding can be done?
Data Binding happens between the HTML (template) and typescript (component). Data binding can be done in 3 ways:

(i) Property Binding (ii) Event Binding (iii) Two-Way Data Binding. 

What is the purpose of using package.json in the angular project?
With the existence of package.json, it will be easy to manage the dependencies of the project. If we are using typescript in the angular project then we can mention the typescript package and version of typescript in package.json.

Differentiate between ng-Class and ng-Style.
In ng-Class, loading of CSS class is possible; whereas, in ng-Style we can set the CSS style.

What are ngModel and how do we represent it? 
ngModel is a directive which can be applied on a text field. This a two-way data binding. ngModel is represented by [()] 

What is an AsyncPipe in Angular? 
When an observable or promise returns something, we use a temporary property to hold the content. Later, we bind the same content to the template. With the usage of AsyncPipe, the promise or observable can be directly used in a template and a temporary property is not required. 


Links 
https://www.greycampus.com/blog/programming/top-30-interview-questions-and-answers-on-angular-5
