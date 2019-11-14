- Initial Router Setup
- Child Routes
- Nested Child Routes
- Auxiliary Routes
- Nested Auxiliary Routes


### Setup

 - Add <base href="/"> in the index.html on the top, it helps the application to construct routing urls while navigating.
 - Add the AppRoutingModule
   * Create Appng generate module app-routing --flat --module=app
   * ng generate module app-routing --flat --module=app
```
    --flat puts the file in src/app instead of its own folder.
    --module=app tells the CLI to register it in the imports array of the AppModule.
```
 - use routerLink directive to perform navigation.


### Angular Routing

```
@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
```
RouterModule.forRoot()

> The @NgModule metadata initializes the router and starts it listening for browser location changes.

The following line adds the RouterModule to the AppRoutingModule imports array and configures it with the routes in one step by calling RouterModule.forRoot():

```
src/app/app-routing.module.ts
imports: [ RouterModule.forRoot(routes) ],
```

The method is called `forRoot()` because you configure the router at the application's root level. The forRoot() method supplies the service providers and directives needed for routing, and performs the initial navigation based on the current browser URL.

Next, AppRoutingModule exports RouterModule so it will be available throughout the app.

```
src/app/app-routing.module.ts (exports array)
exports: [ RouterModule ]
```
