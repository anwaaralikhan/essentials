
` I like the idea`

> Do structure the app such that you can Locate code quickly, Identify the code at a glance, keep the Flattest structure you can, and Try to be DRY

(Scalable Project Structure)[https://stackoverflow.com/questions/51776177/how-to-define-a-highly-scalable-folder-structure-for-your-angular-6-project?noredirect=1&lq=1]


```
|-- app

     |-- [+] configs
     |
     |
     |-- core
       |-- [+] authentication
       |-- [+] guards
       |-- [+] http
       |-- [+] interceptors
       |-- [+] layout
       |-- [+] mocks
       |-- [+] services
       |-- [+] strategies
       |-- core.module.ts
       |-- router.animations.ts
       |-- template-core.module.ts
       |-- theme.module.ts
       |-- ensureModuleLoadedOnceGuard.ts
       |-- logger.service.ts    
     |
     |     
     |-- modules
       |-- client
           |-- [+] components
           |-- client-routing.module.ts
           |-- client.module.ts
       |--- [+] other modules

     |
     |-- shared
          |-- [+] components
          |-- [+] directives
          |-- [+] pipes
          |-- [+] models
          |-- [+] module
      |
      |-- app-routing.module.ts
      |-- app.module.ts
      |-- etc ...
      |
|-- assets
     |-- images
     |-- icons
     |-- css
          |-- styles.scss

```
