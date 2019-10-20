
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

