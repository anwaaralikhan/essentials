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
- 
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
import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import {HttpClientModule} from '@angular/common/http';
import { LoggingService } from './shared/services/logging.service';


@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    DataTablesModule,
    HttpClientModule,
    NgAlertModule
  ],
  providers: [LoggingService],
  bootstrap: [AppComponent]
})
export class AppModule { }

```
