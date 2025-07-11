## 📘 Angular Interview Question Documentation


### 📌 Question 1 : What is the Main Purpose of Angular?
#### ✅ Answer:
**Angular** is a **TypeScript-based front-end web application framework** developed by Google.

> **Main Purpose:**
> 
> To build **dynamic, single-page web applications (SPAs)** using a **component-based architecture**.


### 🎯 Key Objectives of Angular:

- **Single-Page Applications (SPAs):**
  - Build fast, responsive apps without reloading the full page.
  - Routing is used for navigation between views.

- **Component-Based Architecture:**
  - UI is broken into reusable, maintainable components.

- **Two-Way Data Binding:**
  - Synchronizes data between the model (component) and the view (HTML).

- **Dependency Injection:**
  - Enhances code reusability and testability.

- **Built-in Directives & Pipes:**
  - Adds dynamic behavior and formats data efficiently.

- **Powerful Tooling (CLI):**
  - Angular CLI helps with scaffolding, building, testing, and deploying applications.

- **Cross-Platform Support:**
  - Can build web, mobile, and desktop apps (e.g., using Angular Universal, Ionic).

---
### 📌 Question 2 : Difference Between Angular and AngularJS?
#### ✅ Answer:

This document explains the key differences between **AngularJS (v1.x)** and **Angular (v2+)**, focusing on architecture, performance, tooling, and development practices.

### 📌 Overview

| Feature                          | AngularJS (v1.x)                                  | Angular (2+)                                           |
|----------------------------------|---------------------------------------------------|--------------------------------------------------------|
| **Release Year**                 | 2010                                              | 2016                                                   |
| **Architecture**                | MVC (Model-View-Controller)                      | Component-based                                       |
| **Language**                     | JavaScript                                        | TypeScript (superset of JavaScript)                   |
| **Mobile Support**               | Not designed for mobile                           | Designed for mobile-first development                 |
| **Performance**                  | Slower (uses dirty checking for data binding)     | Faster (uses unidirectional data flow + AOT compiler) |
| **Data Binding**                 | Two-way data binding                              | Two-way + unidirectional data binding                 |
| **Dependency Injection (DI)**    | Limited                                           | Built-in and powerful                                 |
| **DOM Manipulation**             | Done directly in controllers                      | Done using directives and components                  |
| **Tooling**                      | Basic (no CLI support)                            | Advanced (Angular CLI, Ivy, RxJS, etc.)               |
| **Routing**                      | Provided via third-party libraries                | Built-in with Angular Router                          |
| **Modularity**                   | Not fully modular                                 | Fully modular with NgModules                          |
| **Testing**                      | Supported but limited                             | Strong testing support (Karma, Jasmine, TestBed)      |
| **Support**                      | No longer officially supported by Angular team    | Actively maintained and supported                     |

### ✅ Key Differences

- **AngularJS** is a legacy JavaScript-based framework (v1.x) using MVC architecture.
- **Angular** (v2+) is a complete rewrite using TypeScript and modern component-based architecture.
- Angular provides better **performance**, **tooling**, and **scalability**.
- AngularJS is **no longer supported** by the Angular team as of January 2022.


### 📚 Use Case Recommendation

| Use Case            | Recommendation  |
|---------------------|-----------------|
| New Projects        | Use **Angular** |
| Maintaining legacy apps | Use **AngularJS** only if existing app is built with it |

## 📦 Additional Resources
- [Upgrade Guide](https://angular.io/guide/upgrade)

---
### 📌 Question 3: What is Ivy and how does it improve performance?
#### ✅ Answer:

**Ivy** is Angular’s default rendering and compilation engine introduced in **Angular 9**. It replaces the older View Engine to make Angular apps **faster**, **smaller**, and **easier to debug**.

---

#### ⚡ How Ivy Improves Performance

- ✅ **Smaller bundle size** via advanced tree shaking.
- 🚀 **Faster compilation** with incremental builds.
- 🔍 **Better debugging** using readable template stack traces.
- 🔄 **Efficient change detection** with optimized checks.
- 📦 **Improved lazy loading** and component-level compilation.

---

### 📌 Question 4 : What is diffrential loading in angular?
#### ✅ Answer:
**Differential Loading** in Angular is a strategy used to improve application performance by loading different bundles of code based on the browser's capabilities.

> **Modern Bundle (ES2015+):** For modern browsers that support ES6+.

> **Legacy Bundle (ES5):** For older browsers that don’t support modern JavaScript.

- Create two versions of your main.js, polyfills.js, etc.
- Add <script> tags with the correct attributes (type="module" and nomodule") in index.html.

```
<script type="module" src="main-es2015.js"></script>
<script nomodule src="main-es5.js"></script>
```
### 🎯 Purpose of Differential Loading:

- To **optimize performance** for modern browsers by reducing bundle size.
- To maintain **backward compatibility** with older browsers (like Internet Explorer 11).

When you build the Angular app using the CLI (Angular 8+):

 ` ng build --prod `

---
### 📌 Question 5: What is purpose of Zone.js in Angular?
#### ✅ Answer:
**Zone.js** is a library used in Angular to perform **automatic change detection** by tracking asynchronous operations like:

- `setTimeout`, `setInterval`
- Promises
- DOM events
- XHR requests

----
### 📌 Question 6: What is AOT compilation in angular?
#### ✅ Answer:

**AOT (Ahead-of-Time) Compilation** in Angular refers to the process of **compiling Angular HTML and TypeScript code into efficient JavaScript code during the build time**, before the browser downloads and runs the application.

Used to improve application performance and reduce the amount of work done in the browser at runtime.

- In Angular CLI (production mode), AOT is **enabled by default**:
  
```
  ng build --prod
```

### 🛠 Key Benefits:

- ✅ **Faster Rendering**: Templates are precompiled, so the browser loads and renders the app faster.
- ✅ **Smaller Angular Framework**: The compiler is not shipped with the app, reducing bundle size.
- ✅ **Early Detection of Errors**: Catches template binding and type-related errors at build time.
- ✅ **Better Security**: Templates are compiled into JavaScript, reducing injection attacks (e.g., XSS).

---
### 📌 Question 7: What is JIT compilation in angular?
#### ✅ Answer:
**JIT (Just-in-Time) Compilation** is a process where Angular compiles your application **in the browser at runtime**.
- To convert Angular HTML templates and TypeScript into JavaScript in the browser just before execution.

#### 🛠 Key Features:

- Faster builds, ideal for development.
- Compiles templates and code on the fly.
- Includes Angular compiler in the bundle.
- Template errors are caught **at runtime**, not during build.
- Slower initial load.
- Larger bundle size compared to AOT.

---
### 📌 Question 8: Difference Between AOT and JIT?
#### ✅ Answer:

| Feature              | AOT (Ahead-of-Time)         | JIT (Just-in-Time)            |
|----------------------|-----------------------------|-------------------------------|
| Compilation Time     | Build time                  | Runtime (in browser)          |
| Performance          | Better (precompiled)        | Slower                        |
| Error Detection      | Build time (early)          | Runtime (late)                |
| Bundle Size          | Smaller                     | Larger (includes compiler)    |
| Development Use      | Not preferred (slow builds) | Preferred (faster builds)     |
| Security             | More secure                 | Less secure                   |

- Use **JIT** during development.
- Use **AOT** for production to improve performance and security.

---

### 📌 Question 9 : How do you enable compilation in Angular?
#### ✅ Answer:

In Angular, you can use **JIT** or **AOT** compilation using CLI commands.
- ***JIT***  default in development
  ```
  ng serve
  
  ```
- ***AOT***  default in production
  ```
  ng build --prod or ng build --aot
  
  ```
---


### 📌 Question 10: What are components and Module in Angular?
#### ✅ Answer:
> 🔹 Component:
A component is the building block of Angular applications. It controls a part of the UI.

- .ts file (logic)
- .html file (template)
- .css/.scss file (styles)

>🔹 Module:
- A module is a container that groups components, directives, pipes, and services.
- Angular apps have at least one root module: AppModule.


---
### 📌 Question 11 : What are decorators in Angular?
#### ✅ Answer:
- Decorators are special declarations used to attach metadata to classes, methods, properties, or parameters.
- In Angular, classes are used to define components, services, and other building blocks of the application (ex.@Component,@Injectable).
- They tell Angular how to process a class or element.
### 🔹 Common Angular Decorators:

| **Decorator**   | **Purpose**                                       |
|-----------------|---------------------------------------------------|
| `@Component`    | Declares a component                              |
| `@NgModule`     | Declares a module                                 |
| `@Injectable`   | Makes a class available for Dependency Injection  |
| `@Input`        | Passes data from parent to child component        |
| `@Output`       | Sends data from child to parent component         |
| `@Directive`    | Declares a custom directive                       |
| `@Pipe`         | Declares a pipe for data transformation           |

----
### 📌 Question 12: What is metadata or annotations in Angular?
#### ✅ Answer:

- Metadata in Angular is used to tell Angular how to process a class. It is added using **decorators**, which are special functions prefixed with `@`.

- Decorators attach metadata to classes, methods, properties, or parameters to define their purpose in the Angular framework.

- Without metadata, Angular won't know how to use your class.
***Metadata(Types)***
@Component, @Input, @Output, @Injectable, @Pipe, @Directive, @NgModule

---
### 📌 Question 13 : What is the importance of Angular component hooks/life cycles?
#### ✅ Answer:
**Angular component lifecycle hooks** are special methods that provide insight into key moments in a component’s life — from creation to destruction.

> Lifecycle hooks allow you to run **custom logic** at specific points in a component’s lifespan.

- 🔁 **Manage initialization and cleanup** (e.g., fetch data in `ngOnInit`, clean subscriptions in `ngOnDestroy`)
- 👁 **Respond to changes in input properties** using `ngOnChanges`
- 🛠 **Access the DOM** after view or content initialization via `ngAfterViewInit`, `ngAfterContentInit`
- 🧪 Useful for **debugging and performance optimization**

### 🔄 Commonly Used Lifecycle Hooks:

| Hook               | Purpose                                                   |
|--------------------|------------------------------------------------------------|
| `ngOnInit()`       | Called once after the component is initialized             |
| `ngOnChanges()`    | Called when `@Input()` properties change                   |
| `ngOnDestroy()`    | Called just before the component is destroyed (cleanup)    |
| `ngAfterViewInit()`| Called after the component's view (and child views) are initialized |
| `ngDoCheck()`      | Called during every change detection run                   |

----
### 📌 Question 14 : Explain Angular life cycle hooks in detail.
#### ✅ Answer:

Angular provides a set of eight core lifecycle hooks that can be implemented in components and directives, each serving a distinct purpose and executing at a specific time: 

#### ngOnChanges():
- This hook is invoked whenever Angular detects changes to data-bound input properties.
- It receives a current and previous values of the changed properties.

#### ngOnInit():
- Called after the initial ngOnChanges() (or first if no inputs are present), 
- Used for component initialization logic, such as fetching initial data from services or setting up subscriptions.

#### ngDoCheck():
- This hook is triggered during every change detection cycle,
- allowing developers to implement custom change detection logic or respond to changes not detected by Angular's default mechanism. 

#### ngAfterContentInit():
- Invoked once after the content (projected content using <ng-content>) has been initialized.
- This is a suitable place to perform initialization tasks related to the content.

#### ngAfterContentChecked(): 
- Called after ngAfterContentInit() and every subsequent ngDoCheck()
- this hook is used to respond to changes detected within the projected content.

#### ngAfterViewInit(): 
- Executed once after the component's view and child views have been initialized. It's a good place to access and manipulate the component element after the view is created.

#### ngAfterViewChecked(): 
- Triggered after every change detection cycle that checks the component's view and child views. 
Use this hook to perform actions after the view has been checked, but be cautious of potential performance impact due to its frequent execution.
#### ngOnDestroy():
- Angular destroys the component instance. 
- This hook is  performing cleanup tasks, such as unsubscribing from observables, detaching event handlers, or releasing resources to prevent memory leaks. 

----
### 📌 Question 15: Differentiate between constructor and ngOnInit().
#### ✅ Answer:
In Angular, both `constructor` and `ngOnInit()` are used during component initialization, but they serve different purposes.

| Feature            | `constructor`                                  | `ngOnInit()`                                         |
|--------------------|------------------------------------------------|------------------------------------------------------|
| **Purpose**        | Initializes the class and injects dependencies | Executes custom logic after Angular sets up the component |
| **Called By**      | TypeScript (when class is instantiated)        | Angular (after the first change detection cycle)     |
| **Timing**         | First method called when the class is created  | Called after constructor and `@Input()` properties are set |
| **Use Case**       | For dependency injection, basic setup          | For API calls, DOM interaction, subscribing to Observables |
| **Access to @Input** | ❌ Not safe to use `@Input()` values          | ✅ `@Input()` values are available                   |

----
### 📌 Question 16: What is change detection in Angular?

#### ✅ Answer:

**Change Detection** in Angular is the process by which the framework **updates the DOM** whenever the **component’s state (data) changes**.

> It ensures that the view (UI) and the model (component data) are always in sync.

#### 🔄 How Change Detection Works:

- Angular runs **change detection** after any asynchronous event (e.g., click, HTTP call, timer).
- It checks the component’s template for changes in the data.
- If any change is found, Angular updates the DOM accordingly.

#### 🔁 Triggered By:

- Browser events (click, keyup, etc.)
- HTTP requests
- Timers (`setTimeout`, `setInterval`)
- Observables / Promises
- `@Input()` property changes

#### ⚙️ Change Detection Strategy:

Angular provides two strategies:

| Strategy            | Description                                      |
|---------------------|--------------------------------------------------|
| `Default`           | Checks every component in the component tree     |
| `OnPush`            | Checks only when input properties change or an event occurs |

----
### 📌 Question 17: How does Angular handle change detection?
#### ✅ Answer:
Angular uses a **Change Detection mechanism** to keep the component's view (DOM) in sync with its data (model).
#### 🔄 How Angular Handles Change Detection:

- **Zone.js Integration**:
   - Angular uses **Zone.js** to intercept and track all async operations (e.g., click, HTTP calls, timers).
   - When an async task completes, Zone.js triggers Angular's change detection automatically.

- **Component Tree Traversal**:
   - Angular starts from the root component and **recursively checks** all child components.
   - For each component, it compares the **current data** with the **template bindings** to detect changes.

- **Template Re-evaluation**:
   - Angular evaluates all data-bound expressions in the component's template.
   - If changes are found, it updates the DOM accordingly.

### ⚙️ Optimization with `ChangeDetectionStrategy`:

| Strategy   | Description                                                   |
|------------|---------------------------------------------------------------|
| `Default`  | Angular checks all components in the tree on every change     |
| `OnPush`   | Angular only checks the component if its `@Input()` data changes or an event occurs |

Use `OnPush` for performance optimization in large applications.


----
### 📌 Question 18: What is OnPush change detection strategy?

#### ✅ Answer:

The `OnPush` change detection strategy is an optimization technique in Angular that **limits when change detection runs** for a component.

> With `OnPush`, Angular only checks the component when:
> - An `@Input()` reference changes
> - An event is triggered in the component
> - You manually trigger it (e.g., using `ChangeDetectorRef`)


```ts
import { ChangeDetectionStrategy, Component } from '@angular/core';

@Component({
  selector: 'app-profile',
  templateUrl: './profile.component.html',
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class ProfileComponent {
  @Input() user: any;
}
```

----
### 📌 Question 19 : What are templates in Angular?

#### ✅ Answer:
A **template** in Angular defines the **HTML view** of a component. It combines standard HTML with **Angular template syntax** to render dynamic content and respond to user interactions.

> Templates are the **UI layer** of a component and are tightly coupled with the component's class.

> **Inline Template** – defined using the `template` property in the `@Component` decorator.
   ```ts
   @Component({
     selector: 'app-inline',
     template: `<h1>Hello {{name}}</h1>`
   })
   export class InlineComponent {
     name = 'Angular';
   }
```
> **External Template** – defined in a separate HTML file using the `templateUrl` property.
```
@Component({
  selector: 'app-external',
  templateUrl: './external.component.html'
})
export class ExternalComponent {
  name = 'Angular';
}
```
---

### 📌 Question 20: What are Directives in Angular and How Many Types of Directives Exist?
#### ✅ Answer:

**Directives** in Angular are special classes that **modify the behavior or appearance of DOM elements**.

> Directives add structure, behavior, or styling logic to your HTML elements or components.
>

Angular provides **three main types** of directives:

| Type                | Description                                                                            | Example                  |
|---------------------|----------------------------------------------------------------------------------------|--------------------------|
| **Component**       | A directive with a template. The most common type.                                     | `@Component`             |
| **Structural**      | Changes the **structure** of the DOM (adds/removes elements).                          | `*ngIf`, `*ngFor`, `*ngSwitch` |
| **Attribute**       | Alters the **appearance or behavior** of an existing element.                          | `ngClass`, `ngStyle`, custom directives |

----

### 📌 Question 21 : Explain Data Binding in Angular and the Different Types?
#### ✅ Answer:
**Data Binding** in Angular is the mechanism that allows communication between the **component (TypeScript)** and the **template (HTML)**.

> It ensures that changes in the component’s data are reflected in the view and vice versa.

### 🔄 Types of Data Binding in Angular:
Angular supports **four main types** of data binding:

| Type               | Syntax                    | Direction            | Description                                              |
|--------------------|---------------------------|----------------------|----------------------------------------------------------|
| **Interpolation**  | `{{ value }}`             | Component ➜ Template | Displays data from the component in the view            |
| **Property Binding** | `[property]="value"`     | Component ➜ Template | Binds DOM property to a component field or expression    |
| **Event Binding**  | `(event)="handler()"`     | Template ➜ Component | Executes component method when DOM event occurs         |
| **Two-way Binding**| `[(ngModel)]="value"`     | Both ways            | Syncs data between component and view using `ngModel`    |

---
### 📌 Question 22: What is a template reference variable?

#### ✅ Answer:
A **template reference variable** in Angular is a reference to a DOM element or Angular component/directive defined in a template. It is declared using the `#` symbol.

- Template reference variables are declared in the template using the hash symbol (#)
- It allows access to the input element’s properties and methods in the component template.

```
 <input #usernameInput type="text">
 <button (click)="logValue(usernameInput.value)">Log Value</button> 
```
- Accessing in the Component
To access a template reference variable in the component's TypeScript file, the `@ViewChild` decorator is used
```
import { Component, ViewChild, ElementRef } from '@angular/core';

@Component({
  selector: 'app-my-component',
  template: `
    <input #myInput type="text">
    <button (click)="focusInput()">Focus</button>
  `
})
export class MyComponent {
  @ViewChild('myInput') myInputField: ElementRef;

  focusInput() {
    this.myInputField.nativeElement.focus();
  }
}
```
----
### 📌 Question 23: What are entry components in Angular?

#### ✅ Answer:
In Angular, **entry components** are components that are **loaded dynamically** at runtime rather than being referenced in a template or a route.

### 📌 Why Do We Need Entry Components?

When Angular compiles the application, it normally includes only those components that are:
- Used in a template (`<app-header>`)
- Defined in a route
----
### 📌 Question 24: What is a Pure Pipe vs. an Impure Pipe?

#### ✅ Answer:

In Angular, **pipes** are used to transform data in templates. Pipes can be **pure** or **impure**, depending on how Angular executes them during change detection.

---

### 🔹 Pure Pipe

- A **pure pipe** is executed **only when its input value or reference changes**.
- It is **stateless and side-effect free**.
- All custom pipes are **pure by default**.


```ts
@Pipe({
  name: 'pureExample'
})
export class PureExamplePipe implements PipeTransform {
  transform(value: string): string {
    return value.toUpperCase();
  }
}
```
### 🔸 Impure Pipe
An **impure pipe** is executed on every change detection cycle, even if the input hasn’t changed.
- Can be stateful or have side effects.
- Must explicitly set pure: false.
- When dealing with mutable data like arrays or objects that change internally.

```
Pipe({
  name: 'impureExample',
  pure: false
})
export class ImpureExamplePipe implements PipeTransform {
  transform(items: any[]): any[] {
    return items.filter(item => item.active);
  }
}
```

----
### 📌 Question 25: What are pipes in Angular?

#### ✅ Answer:
> Pipes in Angular are used to transform data in templates. They take in data and return a transformed version of that data.
- Built-in ```date , uppercase, lowercase, currency, percent, json, slice, async ```
- Custom pipes

``` {{ 1234.56 | currency:'INR' }} ```
----
### 📌 Question 26 : Can you give examples of inbuilt Angular pipes?

#### ✅ Answer:
    1. DatePipe
    2. UpperCasePipe / LowerCasePipe
    3. CurrencyPipe
    4. PercentPipe
    5. DecimalPipe
    6. JsonPipe
    7. SlicePipe
    8. TitleCasePipe
    9. AsyncPipe

----
### 📌 Question 27 : How do you write a custom pipe in Angular?

#### ✅ Answer:
 - Using Angular CLI commad

  ` ng generate pipe custom `

- file will create  `custom.pipe.ts` and `custom.pipe.spec.ts `
```
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'capitalize'
})
export class CapitalizePipe implements PipeTransform {
  transform(value: string): string {
    if (!value) return '';
    return value[0].toUpperCase() + value.slice(1).toLowerCase();
  }
}

@NgModule({
  declarations: [CapitalizePipe],
  exports: [CapitalizePipe]
})
export class SharedModule { }

<p>{{ 'angular' | capitalize }}</p>
<!-- Output: Angular -->
```
----
### 📌 Question 28 : How does dependency injection work in Angular?
#### ✅ Answer:
 - **Dependency Injection (DI)** in Angular is a design pattern where services or dependencies are provided to a class, instead of the class creating them itself. Angular has a built-in injector system that handles this process automatically.
 - You define a service or dependency with the `@Injectable()` decorator.
 - You declare it in a class constructor.
----

### 📌 Question 29 : What are Services in Angular?
#### ✅ Answer: 
 - Services in Angular are reusable classes that contain logic, data, or functions that you want to share across components.
 - Handle data fetching (e.g., via HTTP).
 - Manage state or shared data between components, Improve code reusability.

   `ng generate service <service-name>`
----
### 📌 Question 30 : What is a Singleton Service in Angular?

#### ✅ Answer:
   - A singleton service in Angular is a service that is instantiated only once during the lifetime of the application and is shared across all components and modules that inject it.

- Ensures shared state across components (e.g., user session, cart items).
- Saves memory by reusing the same instance.

Useful for caching, logging, global configuration, etc.

 ```import { Injectable } from '@angular/core';
@Injectable({
  providedIn: 'root'  // Registers it at root level (singleton)
})
export class DataService {
  getCourses() {
    return ['Angular', 'React', 'Vue'];
  }
}
```
----
### 📌 Question 31 : What are template-driven forms in Angular?

#### ✅ Answer:
- **Template-driven forms** in Angular are forms where the logic and structure of the form are mostly defined in the template (HTML), rather than in the component class.
- They are suitable for **simpler forms** and rely heavily on Angular’s directives and **two-way data binding**.
- Uses `[(ngModel)] and  FormsModule`for two-way binding.
- Suitable for small to medium-sized forms.
- Less code in the TypeScript component.

```
<form #userForm="ngForm" (ngSubmit)="onSubmit(userForm)">
  <input name="username" [(ngModel)]="user.name" required />
  <input type="email" name="email" [(ngModel)]="user.email" required />
  <button type="submit">Submit</button>
</form>

```
----
### 📌 Question 32 : What are reactive forms in Angular?
#### ✅ Answer:
- Reactive Forms in Angular are forms that are defined and managed entirely in the component class. They provide more **control, predictability, and scalability, especially for complex or dynamic forms**.
- Requires ReactiveFormsModule

- Use for complex, dynamic, and large-scale forms
- They are also known as **model-driven forms**.
- **FormControl, FormGroup, and FormBuilder**
----
### 📌 Question 33 : What are the key differences between template-driven and reactive forms?
#### ✅ Answer:
Angular supports two main types of forms:
- **Template-Driven Forms** — suitable for simple forms, driven by the template (HTML).
- **Reactive Forms** — suitable for complex forms, driven by the component class (TypeScript).


| Feature                    | Template-Driven Forms                          | Reactive Forms                                    |
|----------------------------|-------------------------------------------------|---------------------------------------------------|
| **Form Setup**             | Defined in the template using directives        | Defined in the component using APIs               |
| **Code Location**          | Mostly in HTML template                        | Mostly in TypeScript component                    |
| **Form Model**             | Created by Angular implicitly                  | Created explicitly by the developer               |
| **Data Binding**           | Uses `[(ngModel)]` for two-way binding         | Uses `formControlName` with reactive APIs         |
| **Validation**             | Uses template directives (`required`, etc.)    | Uses `Validators` from `@angular/forms`           |
| **Testing**                | Harder to test                                 | Easier to test programmatically                   |
| **Scalability**            | Best for simple forms                          | Best for large and dynamic forms                  |
| **Change Detection**       | Automatic via Angular                          | Controlled via API (e.g. `updateOn`)              |
| **Dynamic Fields**         | Difficult to manage                            | Easily managed using `FormArray` and logic        |
| **Module Required**        | `FormsModule`                                  | `ReactiveFormsModule`                             |

----
### 📌 Question 34:  How do you handle form validation in Angular?

#### ✅ Answer:
- In Angular, form validation can be handled using both **Template-Driven Forms** and **Reactive Forms**.
- Use HTML5 validation attributes like **required, minlength, maxlength**, etc.
- Angular automatically adds form validation logic.
- validators in the component using Angular's Validators API.

| **Validator**               | **Description**                                          |
|----------------------------|----------------------------------------------------------|
| `Validators.required`       | Field must not be empty                                 |
| `Validators.min(n)`         | Value must be greater than or equal to `n`              |
| `Validators.max(n)`         | Value must be less than or equal to `n`                 |
| `Validators.minLength(n)`   | Minimum number of characters required                   |
| `Validators.maxLength(n)`   | Maximum number of characters allowed                    |
| `Validators.email`          | Validates correct email format (e.g., `test@example.com`) |
| `Validators.pattern(regex)` | Validates input against a regular expression pattern    |


----
### 📌 Question 35: What is FormBuilder in Angular?

#### ✅ Answer:
- **FormBuilder** is a service provided by Angular’s Reactive Forms module that simplifies the process of creating form **FormControl, FormGroup, and FormArray**. It reduces boilerplate code and makes reactive forms more concise and readable.
----

### 📌 Question 36: How do you handle form submission in Angular?

#### ✅ Answer:
#### 1.  Template-Driven form

```
<form #userForm="ngForm" (ngSubmit)="onSubmit(userForm)">
  <input name="name" ngModel required />
  <button type="submit">Submit</button>
</form>

import { NgForm } from '@angular/forms';

onSubmit(form: NgForm) {
  if (form.valid) {
    console.log('Form Data:', form.value);
  }
}
```
#### 2. Reactive Form

```
<form [formGroup]="form" (ngSubmit)="onSubmit()">
  <input formControlName="name" />
  <button type="submit" [disabled]="form.invalid">Submit</button>
</form>

import { FormBuilder, FormGroup, Validators } from '@angular/forms';

form: FormGroup;

constructor(private fb: FormBuilder) {
  this.form = this.fb.group({
    name: ['', Validators.required]
  });
}

onSubmit() {
  if (this.form.valid) {
    console.log('Form Data:', this.form.value);
  }
}

```
----

### 📌 Question 37: How do you reset a form in Angular?

#### ✅ Answer:
- Template-Driven	**form.reset()**
- Reactive          **form.reset() or form.reset({})**
----

### 📌 Question 38 : How do you handle conditional validation in Angular forms?:

#### ✅ Answer:
```
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

form: FormGroup;

constructor(private fb: FormBuilder) {
  this.form = this.fb.group({
    subscribe: [false],
    email: ['']
  });

  this.handleConditionalValidation();
}

handleConditionalValidation() {
  this.form.get('subscribe')?.valueChanges.subscribe((checked: boolean) => {
    const emailControl = this.form.get('email');
    if (checked) {
      emailControl?.setValidators([Validators.required, Validators.email]);
    } else {
      emailControl?.clearValidators();
    }
    emailControl?.updateValueAndValidity();
  });
}
```

----
### 📌 Question 39: What are async validators in Angular forms?

#### ✅ Answer:
- Async Validators in Angular are used to perform asynchronous validation, such as checking the availability of a username or email on a server. They return an Observable or Promise and are executed after synchronous validators.
----
### 📌 Question 40 : How do you dynamically add form fields in Angular?
#### ✅ Answer:
 - In Angular, you can dynamically add form fields using FormArray — a powerful feature of Reactive Forms.


----
### 📌 Question 41: Explain the importance of routing in Angular & how to implement it.
#### ✅ Answer:
- Routing in Angular enables Single Page Application (SPA) behavior by mapping URLs to components.
- Deep linking and browser history support
- Route protection via guards
- Lazy loading support for better performance
- Seamless SPA navigation
----
### 📌 Question 42: What is SPA and how do you implement it in Angular?

#### ✅ Answer:
- A Single Page Application (SPA) is a web application that loads a single HTML page and dynamically updates the content as the user interacts with the app, without refreshing the entire page.
----
## 📌 Question 43:

### ✅ Answer:
----
## 📌 Question 44:

### ✅ Answer:
----
## 📌 Question 45:

### ✅ Answer:
----
## 📌 Question 46:

### ✅ Answer:
----
## 📌 Question 47:

### ✅ Answer:
----
## 📌 Question 48:

### ✅ Answer:
----
## 📌 Question 49:

### ✅ Answer:
----
## 📌 Question 50:

### ✅ Answer:
----
## 📌 Question 51:

### ✅ Answer:
----
## 📌 Question 52:

### ✅ Answer:
----
## 📌 Question 53:

### ✅ Answer:
----
## 📌 Question 54:

### ✅ Answer:
----
## 📌 Question 55:

### ✅ Answer:
----
## 📌 Question 56:

### ✅ Answer:
----
## 📌 Question 57:

### ✅ Answer:
----
## 📌 Question 58:

### ✅ Answer:
----
## 📌 Question 59:

### ✅ Answer:
----
## 📌 Question 60:

### ✅ Answer:
----
## 📌 Question 61:

### ✅ Answer:
----
## 📌 Question 62:

### ✅ Answer:
----

