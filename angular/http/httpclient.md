## Angular HttpClient


The Angular 8 HttpClient simplified the client HTTP API on the XMLHttpRequest interface exposed by browsers. The Angular HttpClient has features of testability features, typed request and response objects, request and response interception, Observable APIs, and streamlined error handling. This module already included when creating a new Angular app. We just need to register it this Angular app. Open and edit `src/app/app.module.ts` then add this import of HttpClientModule that is part of @angular/common/http.


```
import { HttpClientModule } from '@angular/common/http';
```
Add it to @NgModule imports array after the BrowserModule.


imports: [
  BrowserModule,
  HttpClientModule
],
Now, the Angular HttpClient is ready to use or inject with the Angular service or component.

