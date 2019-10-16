What are pipes in angular

Angular pipes, a way to write display-value transformations that you can declare in your HTML.
Angular comes with a stock of pipes such as DatePipe, UpperCasePipe, LowerCasePipe, CurrencyPipe, and PercentPipe. They are all available for use in any template.

Parameterizing a pipe
A pipe can accept any number of optional parameters to fine-tune its output. To add parameters to a pipe, follow the pipe name with a colon ( : ) and then the parameter value (such as currency:'EUR'). If the pipe accepts multiple parameters, separate the values with colons (such as slice:1:5)
<p>The hero's birthday is {{ birthday | date:"MM/dd/yy" }} </p>

What are directives in Angular?
Write a component when you want to create a reusable set of DOM elements of UI with custom behaviour. Write a directive when you want to write reusable behaviour to supplement existing DOM elements.
Answer: Directives are one of the core features of Angular. They allow an Angular developer to write new, application-specific HTML syntax. In actual, directives are functions that are executed by the Angular compiler when the same finds them in the DOM. Directives are of three types:

Attribute Directives
Component Directives
Structural Directives

Notes: 
A @Component requires a view whereas a @Directive does not.

Directives add behaviour to an existing DOM element or an existing component instance. One example use case for a directive would be to log a click on an element.

import {Directive} from '@angular/core';

@Directive({
    selector: "[logOnClick]",
    hostListeners: {
        'click': 'onClick()',
    },
})
class LogOnClick {
    constructor() {}
    onClick() { console.log('Element clicked!'); }
}
Which would be used like so:

<button logOnClick>I log when clicked!</button>

Components

To register a component we use @Component meta-data annotation.
Component is a directive which uses shadow DOM to create encapsulated visual behavior called components. Components are typically used to create UI widgets.
Component is used to break up the application into smaller components.
Only one component can be present per DOM element.
@View decorator or templateurl template are mandatory in the component.
Directive

To register directives we use @Directive meta-data annotation.
Directive is used to add behavior to an existing DOM element.
Directive is use to design re-usable components.
Many directives can be used per DOM element.
Directive doesn't use View.

https://stackoverflow.com/questions/32680244/directive-v-s-component-in-angular?rq=1


Q2: What is the minimum definition of a component?
Topic: Angular
Difficulty: ⭐⭐
The absolute minimal configuration for a @Component in Angular is a template. Both template properties are set to optional because you have to define either template or templateUrl.

When you don't define them, you will get an exception like this:

No template specified for component 'ComponentName'
A selector property is not required, as you can also use your components in a route.


Q3: What's the difference between an Angular component and module?
Topic: Angular
Difficulty: ⭐⭐
Components control views (html). They also communicate with other components and services to bring functionality to your app.

Modules consist of one or more components. They do not control any html. Your modules declare which components can be used by components belonging to other modules, which classes will be injected by the dependency injector and which component gets bootstrapped. Modules allow you to manage your components to bring modularity to your app.

Q4: How can I select an element in a component template?
Topic: Angular
Difficulty: ⭐⭐
You can get a handle to the DOM element via ElementRef by injecting it into your component's constructor:

constructor(myElement: ElementRef) { ... }

Q10: Why Incremental DOM Has Low Memory Footprint?
Topic: Angular
Difficulty: ⭐⭐⭐
Virtual DOM creates a whole tree from scratch every time you rerender.

Incremental DOM, on the other hand, doesn’t need any memory to rerender the view if it doesn’t change the DOM. We only have to allocate the memory when the DOM nodes are added or removed. And the size of the allocation is proportional to the size of the DOM change.

