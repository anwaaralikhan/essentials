# NgRx

NgRx is an open source library that provides reactive state management for your Angular applications. Inspired by Redux, NgRx provides a way to maintain..

State management can be performed in following ways

- Through component’s interaction via decorators `@Input` bindings and `@Output` event emitters;
- Through Angular services by using simple variables and `Promises`;
- `Observable` to watch for data changes via `RxJs`.

NgRx is an open source library that provides reactive state management for your Angular applications. Inspired by Redux, NgRx provides a way to maintain data in your Angular application as a single source of truth. NgRx uses streams to interact with a data store. 

This data store connects to your components and services, and ultimately simplifies the entire process of data management in your Angular application. 

Instead of injecting services everywhere and managing communication between them, NgRx manages your application from one singular source. Using NgRx, you work with your application in terms of its overall state, instead of individual components.


How NgRx works
There are five parts that constitute NgRx:

Store
Reducers (and Meta-Reducers)
Actions
Selectors
Effects
The basic implementation looks like the following:

![Image description](https://res.cloudinary.com/indepth-dev/image/upload/f_auto,fl_lossy,q_auto/local_media/2019/08/image-276.png)


- Your application’s state is maintained in the store. The store is immutable.
- Your application’s components can subscribe to the store and get automatic updates of state through selectors.
- Selectors enable components to get a slice (a part) of your application’s state, and also mutate state with selector functions.
- Actions modify the state of the store by using reducers (functions) that enable changes while keeping it immutable.
- Meta-Reducers (not shown) are hooks where you can pre or post-process actions before they get invoked.
Effects occur as a result from actions, and can also create actions when called. Effects primary responsibility is to create async side-effects (like service calls to APIs), that ultimately generate other actions.
