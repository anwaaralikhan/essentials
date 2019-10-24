There are three level @ where we can provide services.
- Component
- Module (provider :[])
- Injectable decorator (Angular default way of providing services)


### @Injectable

- @Injectable decorator allows a service to be injectable
- @Injectable decoratoralso provides metadata which tells angular to inject it to components as dependency.
- The injector reuses service whenver possible


### Component 
```import { LoggingService } from './shared/services/logging.service';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css'],
  providers: [LoggingService]
})```
