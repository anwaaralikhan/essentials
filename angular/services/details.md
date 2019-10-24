
> The sole purpose of the service is to share data between child’s components and to provide a couple of helper’s methods.

## Services

1.To Implement any Business Logic that is independent of any Component

Assume you want to calculate the age from DOB, Now you provide the year and The logic can give you age you would not need an HTML view to do that ,it is component Independent

2. Access to Shared Data.

When passing data between components that lack a direct connection, such as siblings, grandchildren, etc, you should use a shared service. You could either use RXJS BehaviorSubject or Subject for cross component communication.

The advantage of using BehaviorSubject or a Subject for cross-component interaction over plain getters and setters is you don't need to manually trigger a method to fetch latest data. Whenever the data is changed all the components where service is injected are automatically notified.

3. External Interactions

1.Accessing REST Web Services Using Http

There are three level @ where we can provide services.
- Component
- Module (provider :[])
- Injectable decorator (Angular default way of providing services)


### @Injectable

- @Injectable decorator allows a service to be injectable
- @Injectable decoratoralso provides metadata which tells angular to inject it to components as dependency.
- The injector reuses service whenver possible


### Component 

- This service is only avialable to this Component.
- When you register a provider at the component level, you get a new instance of the service with each new instance of that component. At the component level, register a service provider in the providers property of the @Component() metadata.
```
import { LoggingService } from './shared/services/logging.service';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
  providers: [LoggingService]
})
```


### Module

```
import { LoggingService } from './shared/services/logging.service';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
  ],
  providers: [LoggingService],
  bootstrap: [AppComponent]
})
export class AppModule { }
```


- [-ve] You are not releasing memory

### OnDestroy Hook
Many developers don’t know this, but non-singletons services also have the ngOnDestroy() lifecycle hook. You can use it for cleaning.

```
export class AdminService implements OnDestroy {
  ngOnDestroy() {
    // Clean subscriptions, intervals, etc
  }  
}
```
Also if we call `NgModuleRef.destroy()` or `PlatformRef.destroy()` then `ngOnDestroy` method of singleton providers will be also executed. 



When you register providers in the @Injectable decorator of the service itself, optimization tools such as those used by the CLI's production builds can perform tree shaking, which removes services that aren't used by your app. Tree shaking results in smaller bundle sizes.

Angular module providers (@NgModule.providers) are registered with the application's root injector. Angular can inject the corresponding services in any class it creates. Once created, a service instance lives for the life of the app and Angular injects this one service instance in every class that needs it.



Well, it's recommended to Always register application-wide services with the root AppModule which makes a service singleton(it will live as long as our application lives) but it entirely depends upon the use case.

If the sole purpose of the service is to share data between child’s components and to provide a couple of helper’s methods.

Register it with component providers and make it a non-singleton service.

The benefit is that when Angular destroys the component, Angular will also destroy the service and release the memory that is occupied by it.

Reference 

1- https://angular.io/guide/architecture-services
2- https://stackoverflow.com/questions/50625913/when-we-should-not-use-angular-service/50631080

