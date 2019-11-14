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
Add Routing
