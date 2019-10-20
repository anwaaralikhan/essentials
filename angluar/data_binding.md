
- Databinding

Data binding is a technique to link your data to your view layer. By binding a variable you are telling the framework (Angular) to watch it for changes. 
If changes are detected, the framework takes care of updating the view accordingly.

This is approach is groundbreaking compared to previous coding paradigms. With vanilla JavaScript or even libraries like JQuery it is up to the developer to update the view. 
More often than not, this leads to spaghetti code.


- One way Databinding

Probably the most common way of showing bound values is to display them as children of another DOM-element. In that case, we can reference our variable from the templates using its name surrounded by two braces on each side. Keep in mind that this method does only provide one-way data binding.

```
import { Component } from '@angular/core'

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppComponent {
  name = 'Angular'
}
```


To display the value of the variable called "name" on the screen, we need to create a binding inside the components' template.

```<p>{{ name }}</p>```

Because we are using the braces to differentiate the variable's name from normal text, we can also combine this syntax with just text.

```<p>Hello, my name is {{ name }}!</p>```

Passing bound values as attributes
Some HTML-elements and angular components with inputs require that values are passed to them using attributes. These data-bindings are called property bindings. In that case, we can use a similar syntax, as if we would append the value to the elements' children.

The difference here is, that we are using the syntax with attributes.

One of the elements that take values via attributes is the input-element. So let's take a look at what that looks like:

```<input value="{{ name }}" />```

Because having braces everywhere would look a little bit cluttered, there is an alternative syntax available. Actually, this syntax is the recommended way to use data binding within attributes:

```<input [value]="name" />```

Instead of braces in the content, there are now square brackets surrounding the attribute.

References 

- https://malcoded.com/posts/angular-data-binding/


## Binding to events
Until now we only used data-binding to display the values of variables on the view. But what if we want to react to actions dispatched for the user?

In that case, we want to bind the corresponding event (for example the click-event) to a method in our component.

To do that, we use attributes, with the name of the event we want to bind to, surrounded by round brackets:

```<button (click)="onButtonClicked()">Change Name</button>```

In this example, the method we want to execute is called "onButtonClicked".

Notice that we do not only have to provide a reference to that method (like e.g. in react) but also call that method `onButtonClicked()`.

Of course, we also have to implement that method in our component:

import { Component } from '@angular/core'

```
@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
})
export class AppComponent {
  name = 'Angular'

  onButtonClicked() {
    this.name = 'Charlie'
  }
}
```

#Passing events along
In the case of mouse-events (and others), it is often required to receive the original event, to get access to information like the click-location.

We can pass the original event to our method by using the special "\$event" syntax:

```<button (click)="onButtonClicked($event)">Change Name</button>```

Notice that that parameter has to be exactly spelled like above, including the dollar sign. Afterward, we can receive the event by adding a parameter to our method:

```onButtonClicked(evt: MouseEvent) {
    this.name = 'Charlie'
}```
``````

### What is two-way data binding?
With two-way data binding, the framework (angular) is not only watching your variables for changes. It also keeps track of changes that are made by the user (for example with input-elements) and updates the variables accordingly.

That way, the variables in the code always represent what is displayed in the view.

How to use two-way data binding in angular
Out of the box, two-way data binding is pretty rare in angular. But there is one commonly used directive that makes two-way data binding possible. This directive is called ngModel.

NgModel is part of the angular "FormsModule" and has to be imported into your module manually.

```
import { NgModule } from '@angular/core'
import { BrowserModule } from '@angular/platform-browser'
import { FormsModule } from '@angular/forms'

import { AppComponent } from './app.component'

@NgModule({
  imports: [BrowserModule, FormsModule],
  declarations: [AppComponent],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

NgModel can be used with form-elements like inputs to implement two-way data binding. To do that, we have to use a pretty special syntax: [(ngModel)]. Its a combination of the one-way- and the event binding syntax.

It is used like so:

```<input [(ngModel)]="name" />```

Using this syntax the value of the variable "name" is not only shown as the value of the input, but both values change when the user types into the input field


##How two-way data binding works
It turns out, the combined syntax is no coincidence. It is just a prettier version of a normal data-binding to display the value on the screen and an event binding to update the value of the variable.

The example above can also be written as:

```<input [ngModel]="name" (ngModelChange)="name = $event" />```

Notive that this version is longer but also gives you more control over what happens. Instead of only updating the value of the "name"-variable with the latest event, you could do all kinds of stuff when the values changes. Just bind to a custom method...

###Conclusion
In this tutorial we discovered, how we can use the power of data binding in our angular application.
