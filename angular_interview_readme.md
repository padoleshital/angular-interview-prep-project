# 📘 Angular Interview Preparation Documentation
---

## 1. Introduction to Angular

Angular is a TypeScript-based open-source front-end web application framework developed by Google. It is used to build single-page applications (SPA).
> 🔹 Angular is known for its component-based architecture.

> 🔹  Component are use structuring organizing projects into manageable, reusable parts. 

> 🔹 Version: Angular 2+ (not AngularJS)  
> 🔹 Written in: TypeScript

## 2.  Angular Architecture

Angular is a component-based framework for building scalable web applications. It follows a modular architecture and uses TypeScript for development

### 1.Module (NgModule)

- Angular is a class decorated with @NgModule, It organizing and structuring Angular applications
- It defines how different parts of an application, such as components, directives, pipes, and services, are grouped together and interact

```
@NgModule({              //app.module
  declarations: [AppComponent],
  imports: [BrowserModule],
  bootstrap: [AppComponent]
})
export class AppModule {}
```
### 2. Component

- Angular applications are primarily built in using components
- Component controls View.
- Component contain Template, Style , Selectors
- `templateUrl` or `template`: Specifies the HTML template for the component's view. 
- `StyleUrl` or `Style` :  Specifies the CSS styles applied to the component's view.
- `StyleUrl` : External css 
- `standalone`: A boolean indicating whether the component is a standalone component, meaning it can be used without being declared in an NgModule.
- `imports`: Used in standalone components to declare dependencies on other standalone components, directives, or pipes.
- `metadata`: (decorated with @Component)

```
@Component({
  selector: 'app-user',
  templateUrl: './user.component.html'
})
export class UserComponent {
  name = 'Shital';
}
```
### 3. Templates

A template defines the HTML view of a component. Templates are a key part of Angular's component-based architecture and are used to declare how the UI should be rendered.

- Interpolation `{{ usrname }}` Binds data from component to view
- Property Binding `[src]="imagUrl"` - Binds Element property component to View 
- Event Binding `(click)="onClick()"` 	Listens to DOM events and executes method
- Two-way Binding ` [(ngModel)]="username"` Binds data in both directions (need FormsModule)
- Structural Directive  Adds/removes elements based on condition or iteration	
    ```*ngIf="isVisible" *ngFor="let item of items" ```
- Attribute Binding	`[attr.aria-label]="label"`	Binds attribute values
- Class Binding	`[class.active]="isActive"`	Adds/removes CSS classes
- Style Binding	`[style.color]="color"`	Binds inline styles dynamically

### 4. Services

- Service is a reusable class that contains logic or data that you want to share across multiple components.
- components handle the UI, and services handle the business logic, API calls, data storage, etc
- An Angular service is a TypeScript class decorated with @Injectable() and is typically used for:
    - Fetching data from an API (e.g., via HttpClient)
    - Managing state or business logic
    - Logging
    - Authentication
    - Sharing data between components

`ng generate service my-service`

#### 4. Dependency Injection

- Dependency injection (DI) is a software design pattern that implements the principle of Inversion of Control (IoC)
- Dependency Injection system manages the dependencies between various parts of an application, providing loose coupling(a design principle where software components have minimal dependencies on each other, meaning changes in one component are less likely to affect others) and modular development.

## 4. Component Lifecycle

Angular provides a set of eight core lifecycle hooks that can be implemented in components and directives, each serving a distinct purpose and executing at a specific time: 

### ngOnChanges():
- This hook is invoked whenever Angular detects changes to data-bound input properties.
- It receives a current and previous values of the changed properties.

### ngOnInit():
- Called after the initial ngOnChanges() (or first if no inputs are present), 
- used for component initialization logic, such as fetching initial data from services or setting up subscriptions.

### ngDoCheck():
- This hook is triggered during every change detection cycle,
- allowing developers to implement custom change detection logic or respond to changes not detected by Angular's default mechanism. 

### ngAfterContentInit():
- Invoked once after the content (projected content using <ng-content>) has been initialized.
- This is a suitable place to perform initialization tasks related to the content.

### ngAfterContentChecked(): 
- Called after ngAfterContentInit() and every subsequent ngDoCheck()
- this hook is used to respond to changes detected within the projected content.

### ngAfterViewInit(): 
- Executed once after the component's view and child views have been initialized. It's a good place to access and manipulate the component element after the view is created.

### ngAfterViewChecked(): 
- Triggered after every change detection cycle that checks the component's view and child views. 
Use this hook to perform actions after the view has been checked, but be cautious of potential performance impact due to its frequent execution.
### ngOnDestroy():
- Angular destroys the component instance. 
- This hook is  performing cleanup tasks, such as unsubscribing from observables, detaching event handlers, or releasing resources to prevent memory leaks. 

`ngOnChanges(), ngDoCheck(), ngAfterContentChecked(), ngAfterViewChecked() `can be triggered multiple times throughout the component's lifecycle as change detection runs, while the others are generally called only once.

## 5. Services & Dependency Injection

- Create services using `@Injectable()`
- @Injectable() decorator marks class as an angular service and allows it injected into other component and service.
- providedIn: 'root': This configuration ensures that a single, making it available throughout the entire application as a singleton.

  `ng g service service-name`

    - This will create  service-name.service.ts  and service-name.service.spec.ts file service class.

    ```
     import { Injectable } from '@angular/core';

    @Injectable({
      providedIn: 'root' // Makes the service a singleton available throughout the app
    })
    ```

- Inject services into components using constructor
    - private keyword constructor this ype as the injected service, making it accessible within the component.
  ```
      import { MyDataService } from './my-data.service';

    @Component({
      selector: 'app-my-component',
      template: `
        <p>{{ data }}</p>
      `
    })
    export class MyComponent {
      data: string;

      constructor(private myDataService: MyDataService) { // Inject the service
        this.data = this.myDataService.getData();
      }
    }

  ```


- Singleton pattern
    - A singleton service is a service for which only one instance exists in an application.
```
import { Injectable } from '@angular/core';

    @Injectable({
      providedIn: 'root' // This makes the service a singleton for the entire application
    })
```
```
  @NgModule({
      providers: [MySingletonService], // Providing the service in the root module
      // ... other module configurations
    })
```

---

## 6. Routing & Navigation

- `RouterModule` is part of Angular Router (@angular/router) library for managing navigation in Angular applications and a core part of the framework.
- Routes serve as the fundamental building blocks for navigation within an Angular app.

    ` ng add @angular/router `

- When you need to catch all routes for a specific path, the solution is a wildcard route which is defined with the double asterisk (**).
- When user search for path which is not present routing array that time we use windcard
    `
    import { Home } from './home/home.component';
    import { UserProfile } from './user-profile/user-profile.component';
    import { NotFound } from './not-found/not-found.component';
      const routes: Routes = [
      { path: 'home', component: Home },
      { path: 'user/:id', component: UserProfile },
      { path: '**', component: NotFound }
    ];`


- `RouterOutlet`

  `<nav>
  <a routerLink="/">Home</a>
  <a routerLink="/about">About</a>
</nav>

<router-outlet></router-outlet>`
- Route parameters: `ActivatedRoute`
- Lazy Loading with `loadChildren`

---

## 7. Forms in Angular

- **Template-driven forms**
- **Reactive forms**
- Form validation (`Validators`)
- `FormControl`, `FormGroup`, `FormBuilder`

---

## 8. RxJS & Observables

- Observables: `Observable`, `Subject`, `BehaviorSubject`
- Operators: `map`, `filter`, `switchMap`, `mergeMap`, etc.
- `subscribe()` to listen to data streams

---

## 9. Directives

- **Structural**: `*ngIf`, `*ngFor`, `*ngSwitch`
- **Attribute**: `ngClass`, `ngStyle`, custom directives

---

## 10. Pipes

- Built-in: `date`, `currency`, `uppercase`, `lowercase`
- Custom Pipes using `Pipe` decorator

---

## 11. Change Detection

- `ChangeDetectionStrategy.OnPush`
- Zone.js
- Manual detection with `ChangeDetectorRef`

---

## 12. HTTPClient & APIs

- `HttpClientModule`
- `HttpClient.get()`, `.post()`, `.put()`, `.delete()`
- Observables & error handling (`catchError`, `retry`)

---

## 13. State Management (NgRx)

- Actions, Reducers, Store, Effects
- Alternative: Services with Subjects/BehaviorSubjects

---

## 14. Testing

- Unit tests using Jasmine/Karma
- TestBed for Angular testing
- `ComponentFixture`, `fakeAsync`, `tick()`

---

## 15. Performance Optimization

- Lazy Loading
- AOT Compilation
- TrackBy in `*ngFor`
- OnPush Change Detection
- Avoid memory leaks (unsubscribe Observables)

---

## 16. Interview Questions

**Basic:**

- What is Angular?
- Difference between AngularJS and Angular?
- What are directives?
- Explain data binding.

**Intermediate:**

- What is dependency injection?
- How does routing work?
- Difference between template-driven and reactive forms?
- What is `ngOnInit`?

**Advanced:**

- Explain change detection in Angular.
- What are RxJS subjects?
- How does Angular handle memory leaks?
- What are the benefits of OnPush strategy?

---

## 📚 References

- [Angular Official Docs](https://angular.io/docs)
- [RxJS Docs](https://rxjs.dev/)
- [Angular GitHub](https://github.com/angular/angular)

