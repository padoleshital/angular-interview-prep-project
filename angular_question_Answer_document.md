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
- Angular uses its **RouterModule, routerLink** to implement it
- Loading components dynamically inside a **<router-outlet>** without refreshing the page.
----
### 📌 Question 43: What is a router outlet in Angular?

#### ✅ Answer:
- **router-outlet** is a directive that acts as a placeholder in a component's template.
-  Used to dynamically load different components based on the current URL route.
- Use build single-page applications where different parts of the app can change without reloading the entire page
- Router outlet is install using `ng add @angular/router` librabry
----
### 📌 Question 44 : What is routerLink and how is it used in Angular?

#### ✅ Answer:
- `routerLink` is a directive used to bind a route path to an HTML element, typically an <a> tag or a <button>, enabling navigation between components without reloading the page.

  **Dynamic Routing**
```
<a [routerLink]="['/user', userId]">View User</a>
```
**Navigate using Router service in TypeScript**
```
import { Router } from '@angular/router';

constructor(private router: Router) {}

goToAbout() {
  this.router.navigate(['/about']);
}

```
---

### 📌 Question 45: What is route guarding in Angular?

#### ✅ Answer:
- A **Route Guard** in Angular is a feature that **controls navigation** to and from components based on logic .
- It helps restrict access to certain routes unless specific conditions are met.
- such as user authentication, role-based access, unsaved changes, etc.
- Prevent access to a route unless the user is logged in.
- Prevent navigation away from a form with unsaved changes.
- Restrict access to routes based on user roles or permissions.

----
### 📌 Question 46: What are different types of route guards in Angular?

#### ✅ Answer:

##### ✅ Types of Route Guards in Angular

### 1. `CanActivate`
- **Purpose**: Determines if a route can be activated.
- **Use Case**: Prevent access to routes for unauthenticated users.

### 2.`CanActivateChild`
- **Purpose**: Determines if child routes can be activated.
- **Use Case**: Apply route guard logic to all child routes (e.g., admin section).

### 3.`CanDeactivate<T>`
- **Purpose** : Checks if the user can navigate away from the current route.
- **Use Case**: Prevent form data loss by alerting the user if they try to leave with unsaved changes.

### 4. `CanLoad`
- **Purpose**: Checks if a lazy-loaded module can be loaded.
- **Use Case**: Prevent module loading for unauthorized users.

### 5. `Resolve<T>`
- **Purpose**: Fetch data before the route is activated.
- **Use Case**: Load route-specific data (e.g., user profile) before component initialization.
----
### 📌 Question 47 : How do you implement route guards in Angular?

#### ✅ Answer:
- Use Angular CLI to generate a new guard:
    `ng generate guard auth/auth`
- above command will create
 - ` auth.guard.ts` and  `auth.guard.spec.ts`
 ```    
 // auth.guard.ts
import { Injectable } from '@angular/core';
import { CanActivate, Router } from '@angular/router';
import { AuthService } from './auth.service';

@Injectable({ providedIn: 'root' })
export class AuthGuard implements CanActivate {

  constructor(private authService: AuthService, private router: Router) {}

  canActivate(): boolean {
    if (this.authService.isLoggedIn()) {
      return true;
    } else {
      this.router.navigate(['/login']);
      return false;
    }
  }
}


// app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { DashboardComponent } from './dashboard/dashboard.component';
import { AuthGuard } from './auth/auth.guard';

const routes: Routes = [
  {
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [AuthGuard]
  },
  {
    path: 'login',
    component: LoginComponent
  },
  { path: '**', redirectTo: 'login' }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}


// app-routing.module.ts
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';
import { DashboardComponent } from './dashboard/dashboard.component';
import { AuthGuard } from './auth/auth.guard';

const routes: Routes = [
  {
    path: 'dashboard',
    component: DashboardComponent,
    canActivate: [AuthGuard]
  },
  {
    path: 'login',
    component: LoginComponent
  },
  { path: '**', redirectTo: 'login' }
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}


 ```

----
### 📌 Question 48 : How do you pass data in Angular routes?

#### ✅ Answer:
- Prefer route parameters for IDs or required path data.
- Use query parameters for filters/search/pagination.
- Use static data for access control or metadata.

1. Using **Route Parameters**

```ts
// app-routing.module.ts
{ path: 'user/:id', component: UserComponent }

.html
<a [routerLink]="['/user', 101]">View User</a>

.ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}

ngOnInit() {
  const id = this.route.snapshot.paramMap.get('id');
}
```
2. Using **Query Parameters**

- Query parameters are useful for optional values like filters, page numbers, or sorting.

```
<a [routerLink]="['/products']" [queryParams]="{ category: 'books', sort: 'asc' }">
  View Books
</a>

.ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}

ngOnInit() {
  this.route.queryParamMap.subscribe(params => {
    const category = params.get('category');
    const sort = params.get('sort');
  });
}
```
3. Using **Static Route Data**

- Use this method to associate static configuration or metadata with a route.

```
{ path: 'admin', component: AdminComponent, data: { role: 'admin' } 

.ts
import { ActivatedRoute } from '@angular/router';

constructor(private route: ActivatedRoute) {}

ngOnInit() {
  const role = this.route.snapshot.data['role'];
}
```

----
### 📌 Question 49 : What is a wildcard route in Angular?

#### ✅ Answer:
- In Angular, a wildcard route is a special type of route used to catch all undefined paths—typically when a user navigates to a URL that doesn’t match any existing route.
- It acts as a fallback route, often used to show a "404 Not Found" page.
- ** matches any URL that doesn’t match earlier routes.
- It should always be the last route in the Routes array, because Angular matches routes in order.


----
### 📌 Question 50 : How do you handle route parameters in Angular?

#### ✅ Answer:

- Route parameters allow you to pass dynamic values (like IDs or names) through the URL.
- Angular provides the `ActivatedRoute` service to access these parameters in components.
- Use paramMap when you expect the same component to load with different parameters (e.g., /user/1 → /user/2).
- snapshot - One-time read - Component won't be reused
- paramMap - Observable for param changes - Component reused for new params
----
### 📌 Question 51: What is canActivate and canDeactivate in Angular?

#### ✅ Answer:
- Angular provides **route guards** to control access to certain routes. The two most commonly used guards are:

- `canActivate` – controls **if a route can be activated**
- Used to **prevent unauthorized access** to a route unless certain conditions are met (e.g., authentication, roles).
- Only allow logged-in users to visit the `/dashboard` route.

- `canDeactivate` – controls **if a route can be exited**
- Used to prevent accidental navigation away from a route when a form is dirty or changes are unsaved.

----
### 📌 Question 52: What is a resolver in Angular routing?
#### ✅ Answer:

- A **resolver** in Angular is a service that **pre-fetches data before a route is activated**. It ensures that the component has all the necessary data when it loads, improving the user experience and avoiding flickers or loading states.
- To load data **before** navigating to a route.
- Prevent showing components with incomplete or missing data.
- Centralize route-based data fetching logic.

----
### 📌 Question 53: What is lazy loading in Angular?

#### ✅ Answer:

- **Lazy Loading** in Angular is a technique where **feature modules are loaded** only when they are required, rather than at the initial application load.
- Reducing the initial bundle size.
- Improving app performance and load time.
- Organizing code in a modular way

----
### 📌 Question 54: How do you implement lazy loading in Angular?

#### ✅ Answer:
- Instead of loading everything in **AppModule**, you create feature modules and configure them to load dynamically using **loadChildren**.
- Create a Feature Module cmd command

  `ng generate module products --route products --module app.module`

  ```
  ts
  const routes: Routes = [
  {
    path: 'products',
    loadChildren: () =>
      import('./products/products.module').then(m => m.ProductsModule)
  },
  { path: '', redirectTo: 'home', pathMatch: 'full' }
  ];

  ```
----
### 📌 Question 55: What is tree shaking in Angular?

#### ✅ Answer:
Tree shaking is a **build optimization technique** that removes unused code during the production build process.
- Angular uses **Webpack and ES2015 modules** to perform tree shaking.
- It improves performance by reducing **bundle size**.
- Automatically done when using **ng build --prod**.
----

### 📌 Question 56: What is Webpack and how does Angular use it?

#### ✅ Answer:

  - Webpack is a powerful module bundler for JavaScript applications. It takes your app’s files and dependencies, transforms them, and bundles them into static assets (like JS, CSS, HTML) for deployment.
 - When we run ` ng build` 
 Angular CLI:
- Uses Webpack config under the hood
- Compiles .ts files to .js
- Applies AOT, minification, and optimization
- Generates main.js, polyfills.js, runtime.js, etc.


----
### 📌 Question 57: What is Service Worker in Angular and how is it used?

#### ✅ Answer:
A Service Worker in Angular is a script that runs in the background, separate from the main browser thread, and enables progressive web app (PWA) features such as:
- Offline support
- Background sync
- Push notifications
- Caching static and dynamic assets
- Angular provides built-in support for service workers through the @angular/service-worker package.
----

### 📌 Question 58 : How do you implement server-side rendering (SSR) in Angular?

#### ✅ Answer:
Server-Side Rendering (SSR) in Angular means rendering your Angular application on the server instead of the browser. This improves:
  - SEO (Search Engine Optimization)
  - Faster initial page load
  - Better performance on slow networks
  - Angular uses a platform called Angular Universal to implement SSR.
  - `ng add @nguniversal/express-engine `
----
### 📌 Question 59 : What is Angular Universal?

#### ✅ Answer:
- Angular Universal is a technology provided by Angular that enables Server-Side Rendering (SSR) of Angular applications. 
- It allows your Angular app to be rendered on the server (Node.js) and then delivered to the browser as a fully rendered HTML page.

----

### 📌 Question 60: What is HttpClient in Angular?

#### ✅ Answer:
- **HttpClient** is a service provided by Angular’s @angular/common/http package that allows you to **make HTTP requests (GET, POST, PUT, DELETE, etc.)** to interact with backend APIs or remote servers.

It is **based on Observables from RxJS**, making it easy to handle asynchronous operations like data fetching, error handling, retries, and transformations.


----
### 📌 Question 61 : How do you make an HTTP GET request in Angular?

#### ✅ Answer:
To make an HTTP `GET` request in Angular, you use the `HttpClient` service provided by the `@angular/common/http` module. This allows your app to **retrieve data from a RESTful API**.
  ```
  ts
  getUsers(): Observable<User[]> {
    return this.http.get<User[]>('https://api.example.com/users').pipe(
      catchError(error => {
        console.error('Error:', error);
        return throwError(() => error);
      })
    );
  }
  ```
----
### 📌 Question 62 : How do you make an HTTP POST request in Angular?

#### ✅ Answer:
- To make an `HTTP POST` request in Angular, use the `HttpClient` service from the `@angular/common/http package`. A POST request is used to **send data to a server**, typically for creating a new resource.
  ```
  const headers = new HttpHeaders({ 'Authorization': 'Bearer token' });
  this.http.post('url', body, { headers });

  ```
----
### 📌 Question 63 : How do you handle HTTP errors in Angular?

#### ✅ Answer:
  - In Angular, you handle HTTP errors using the HttpClient service along with RxJS operators like catchError() inside .pipe().
  - This allows you to catch and respond to errors such as:
  - 404 Not Found
  - 500 Internal Server Error
  -  0 Network Error
  -  Unauthorized (401), Forbidden (403), etc.
```
    @Injectable()
    export class ErrorInterceptor implements HttpInterceptor {
      intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
        return next.handle(req).pipe(
          catchError((err: HttpErrorResponse) => {
            alert('Something went wrong!');
            return throwError(() => err);
          })
        );
      }
    }

    providers: [
      { provide: HTTP_INTERCEPTORS, useClass: ErrorInterceptor, multi: true }
    ]

```

| Tool / Concept       | Description                                         |
|----------------------|-----------------------------------------------------|
| `catchError()`       | RxJS operator for catching and managing HTTP errors |
| `HttpErrorResponse`  | Angular's error object containing status, message   |
| `throwError()`       | Returns an Observable that emits an error           |
| `retry()` / `of()`   | Retries the request or provides a fallback value    |
| `Interceptors`       | Centralized, app-wide error handling mechanism      |


----
### 📌 Question 64: How do you use interceptors for HTTP requests?

#### ✅ Answer:
An **HTTP interceptor** is a service that implements the `HttpInterceptor` interface and allows you to:
- Modify **outgoing requests** (e.g., add auth tokens)
- Handle **incoming responses** (e.g., log or transform responses)
- Handle **errors globally**
----
### 📌 Question 65 : How do you use async/await with HttpClient in Angular? 

#### ✅ Answer:
- In Angular, the HttpClient methods (get(), post(), etc.) return Observables, not Promises.
- you can still use async/await by converting the Observable to a Promise using the .toPromise() method (deprecated) or better.

    ```
    import { HttpClient } from '@angular/common/http';
  import { Injectable } from '@angular/core';

  @Injectable({
    providedIn: 'root'
  })
  export class DataService {
    constructor(private http: HttpClient) {}

    async fetchData(): Promise<any> {
      try {
        const response = await firstValueFrom(
          this.http.get('https://api.example.com/data')
        );
        console.log('Data:', response);
        return response;
      } catch (error) {
        console.error('Error:', error);
        throw error;
      }
    }
    ```
----
### 📌 Question 66 : What is the difference between HttpClient and Fetch API?

#### ✅ Answer:

| Feature / Aspect         | **HttpClient (Angular)**                                      | **Fetch API (JavaScript)**                             |
|--------------------------|---------------------------------------------------------------|--------------------------------------------------------|
| 📚 Module                | `@angular/common/http`                                        | Built-in in browsers (ES6+)                            |
| 🔁 Return Type           | `Observable`                                                  | `Promise`                                              |
| ⚙️ Error Handling         | Via RxJS `catchError()`                                       | Only throws on network errors                          |
| 🎯 Status Handling       | Handles all status codes via error/response object            | Must check `response.ok` or `status` manually          |
| 🧠 TypeScript Support    | Strong TypeScript integration                                 | Needs manual typing                                    |
| 🧩 Interceptors Support  | ✅ Yes (for tokens, errors, logging)                           | ❌ No built-in support                                 |
| 🚀 Features              | Auto JSON parsing, headers, retry, progress tracking          | Manual JSON parsing, header setup                      |
| 🧪 Testing               | Easy to mock in Angular unit tests                            | Requires manual mocks                                  |
| 🔄 Cancellation          | Built-in via RxJS `unsubscribe()`                             | Use `AbortController`                                  |
| ♻️ Reusability & DI      | Injectable and testable Angular service                       | Needs custom functions or classes                      |

----
### 📌 Question 67 : What are interceptors in Angular?

#### ✅ Answer:

- Interceptors in Angular are special services that implement the HttpInterceptor interface and allow you to intercept and modify HTTP requests and responses globally.
  
  They are part of Angular's HttpClient module and are commonly used to:
  - Add headers (e.g., authentication tokens)
  - Log requests/responses
  - Handle errors globally

  - Modify outgoing/incoming data
----
### 📌 Question 68 : How do you implement interceptors?
#### ✅ Answer:

    ng generate service interceptors/auth
----
### 📌 Question 69: What are some uses of interceptors, and can we provide multiple interceptors?

#### ✅ Answer:

  
Angular interceptors are powerful tools for handling HTTP requests and responses globally. Below are common and practical use cases where interceptors are highly useful in real-world applications.


| Use Case               | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| 🔐 **Authentication**   | Add JWT or API token to request headers automatically.                     |
| ❗ **Global Error Handling** | Catch and handle all HTTP errors (401, 500, etc.) in one place.             |
| 🧾 **Logging**          | Log every outgoing request or incoming response for debugging and auditing. |
| 🌐 **Set Base URLs**     | Prepend a base URL to all outgoing requests (e.g., `https://api.example.com`). |
| ⏱️ **Loading Indicator** | Trigger loading spinners or progress bars on HTTP start/stop.              |
| 🌍 **Localization**      | Add language headers like `Accept-Language` for internationalization (i18n). |
| ♻️ **Retry Failed Requests** | Automatically retry failed HTTP requests using RxJS `retry()` operator.   |
| 🔐 **Refresh Token**     | Automatically detect expired access tokens and refresh them using refresh tokens. |


## 🔗 Related Topics

- [Creating Interceptors](#)
- [Registering Multiple Interceptors](#)
- [RxJS Operators for Error Handling](#)
- [HTTPClient in Angular](#)


> 📘 Tip: Use `multi: true` while registering interceptors in `AppModule` to chain multiple interceptors together.
----
### 📌 Question 70 : What is RxJs and why is it needed?

#### ✅ Answer:
JavaScript is single-threaded and asynchronous operations (e.g. API calls, user input, timers) need to be handled without blocking the UI.

| Need                         | How RxJS Helps                                                                 |
|------------------------------|----------------------------------------------------------------------------------|
| ⏱️ **Handle async data**       | Observables emit data over time like Promises, but with more capabilities.     |
| 💥 **Manage multiple events**  | Combine, debounce, retry, cancel, or throttle event streams easily.             |
| 🔗 **Chain operations**        | Use operators like `map`, `filter`, `mergeMap`, `switchMap` to transform streams. |
| 🚀 **Simplify Angular features** | Angular forms, HTTP requests, state management, and routing all use RxJS.       |
| ❌ **Cancel subscriptions**    | Observables can be unsubscribed to avoid memory leaks or cancel requests.      |

----

### 📌 Question 71: What are observables and observers?

#### ✅ Answer:
- An Observable is a representation of any stream of data over time (e.g., HTTP responses, user input, timers).
-Sends data (produces stream)
- It is lazy: it doesn’t start producing data until someone subscribes.
- An Observer is an object that defines how to react to values delivered by the Observable. It has up to three callbacks

- next(value) → when a value is emitted
- error(err) → when an error occurs
- complete() → when the stream finishes
----
### 📌 Question 72: What is a stream in RxJs?

#### ✅ Answer:
- A stream is essentially a collection of values over time, emitted by an Observable.

- In RxJS (Reactive Extensions for JavaScript), a stream is a sequence of ongoing events ordered in time, which can be observed and reacted to.
----
### 📌 Question 73: What is the use of subscribe in RxJs?

#### ✅ Answer:

- subscribe() connects an Observer to an Observable so that the Observer can receive data, handle errors, and know when the stream completes.

- Observables are lazy — they don’t run until subscribe() is called.
----
### 📌 Question 74: How do you unsubscribe from a stream?

#### ✅ Answer:
- To stop listening to an Observable, you need to unsubscribe — this prevents memory leaks and stops receiving emitted values.
- Using take(n) or takeUntil() operator.
- If you're using async pipe, Angular automatically unsubscribes for you.


----
### 📌 Question 75: What are operators in RxJs?

#### ✅ Answer:
- There are two type
1. Pipeable Operators - Used inside .pipe() to transform the stream -map, filter, mergeMap, take, catchError
2. Creation Operators  - Create new Observables - of, from, interval, timer
----
### 📌 Question 76: Where have you used RxJs in Angular?

#### ✅ Answer:
- In Angular, RxJS is used everywhere — because Angular is built around reactive programming. Here's where and how you typically use it.
- in form, HTTP, component, routing, event handling etc
----

### 📌 Question 77: Differentiate between RxJs and Promises.

#### ✅ Answer:

| Feature | RxJS (Observables) | Promises |
|--------|---------------------|----------|
| 🔁 **Multiple Values** | Yes (stream of values) | No (single value) |
| ⏱️ **Lazy Execution** | Yes (starts on `subscribe()`) | Yes (starts on creation) |
| ❌ **Cancelable** | Yes (`unsubscribe()`) | No |
| 🧰 **Operators Support** | Yes (`map`, `filter`, `switchMap`, etc.) | No (only `then`, `catch`, `finally`) |
| 🕒 **Time-Based Handling** | Easy (`debounceTime`, `interval`, etc.) | Difficult (manual `setTimeout`) |
| 🔄 **Reusability** | Can be multicasted/shared | One-time use |
| ⚡ **Integration in Angular** | Deep (`HttpClient`, `Forms`, etc.) | Minimal |
| 📤 **Push vs Pull** | Push (reactive) | Pull (imperative) |

- Use Promises for simple, one-time async operations.
- Use RxJS Observables for complex, multi-value, or reactive use cases — especially in Angular.

----
### 📌 Question 78: How do you install RxJs?

#### ✅ Answer:
- For any JavaScript or TypeScript project
 `npm install rxjs`
- install via CDN
- If you're using Angular, RxJS is pre-installed when you create a project using the Angular CL 
----
### 📌 Question 79: Why is RxJs called push/reactive and not pull/imperative?

#### ✅ Answer:
----
### 📌 Question 80: Name some RxJs operators.

#### ✅ Answer:
 - `Map`, `pluck`, `of`, `from`, `interval`, `take`, `fromEvent`, `debounceTime`, `flat`, `Filter`, `SwitchMap`, `MargeMap`, `SwitchMap`
----

### 📌 Question 81 : What is the difference between BehaviorSubject and Subject in RxJS?
#### ✅ Answer:
- **Subject**: 
A `Subject` is a multicast observable that can be subscribed to by multiple observers. 

- It acts as both an observable and an observer, meaning you can subscribe to it to receive values and also push values to it using its `next()` method.

- When a `Subject` emits a new value, all of its subscribed observers will receive that value.

- 2. **BehaviorSubject**: 
- A `BehaviorSubject` is a type of `Subject` that has a notion of “current value”.

- It maintains and emits the latest value to any new subscribers. When a `BehaviorSubject` is created, it requires an initial value. 

- Any subscriber that subscribes to a `BehaviorSubject` will immediately receive the current value or the latest emitted value.



----
### 📌 Question 82: How can you optimize an Angular application’s performance?

#### ✅ Answer:
-  Use OnPush Change Detection - Best for performance-critical or static components
- Lazy Loading Modules - Load features only when needed, reducing initial load time.
- Use Pure Pipes - Pure pipes only run when inputs change — avoid recalculating unnecessarily.
- Avoid Memory Leaks with unsubscribe() -Always unsubscribe from Observables to prevent memory leaks
- Use trackBy in *ngFor = - Improves DOM performance by preventing full re-rendering.
- Minify and Compress Bundles - production build.
- Use async Pipe in Templates - Automatically subscribes and unsubscribes from Observables.
- Avoid Complex Logic in Templates - do not use logic in Templates  

----
### 📌 Question 83: What is the need for Angular CLI?

#### ✅ Answer:
- The Angular CLI (Command Line Interface) is a powerful tool that simplifies the development process
- Using CLI reducing 
- Quickly creates a ready-to-run Angular app also generate component , directive, service, using command .
- Use ng serve to run a development server with live reloading.
- Installs and updates required npm packages easily.
----
### 📌 Question 84: Why do we need ViewChild and ViewChildren in Angular?

#### ✅ Answer:
`ViewChild` and `ViewChildren` are decorators used to **access DOM elements, components, or directives from a component's template**.
- `@ViewChild` 
    ViewChild Access a single element or component from the view.
- `@ViewChildren` 
    ViewChildren allows you to access a QueryList(Multiple Element) of elements for batch operations.
- Best used after the view has initialized (ngAfterViewInit lifecycle hook).
- They are essential for direct communication between `parent and child components`, or for template manipulation in advanced UI scenarios.

----
### 📌 Question 85: Explain ContentChild and ContentChildren

#### ✅ Answer:
- @ContentChild and @ContentChildren are Angular decorators used to access projected content that is passed into a component via <ng-content>.

- They allow the parent component to interact with content projected from outside, such as child components or template references use `ngAfterContentInit()`.

- They’re useful when building flexible and reusable UI components that accept dynamic content from their parent.
- `@ContentChild` - Access a single projected element/component
- `@ContentChildren` - Access multiple projected elements/components.
----
### 📌 Question 86: Differentiate between ViewChild, ViewChildren, ContentChild, and ContentChildren.

#### ✅ Answer:

| Decorator         | Description                                                 | Access Scope         | Returns         | Lifecycle Hook         |
|-------------------|-------------------------------------------------------------|-----------------------|------------------|-------------------------|
| `@ViewChild`      | Accesses a single DOM element, directive, or component      | **Component's own view** | ElementRef / Component | `ngAfterViewInit()`     |
| `@ViewChildren`   | Accesses multiple DOM elements, directives, or components   | **Component's own view** | QueryList        | `ngAfterViewInit()`     |
| `@ContentChild`   | Accesses a single projected content from `<ng-content>`     | **Projected content**     | ElementRef / Component | `ngAfterContentInit()`  |
| `@ContentChildren`| Accesses multiple projected elements from `<ng-content>`    | **Projected content**     | QueryList        | `ngAfterContentInit()`  |

----
### 📌 Question 87: What is { static: true } in ViewChild?

#### ✅ Answer:
    `@ViewChild('myElement', { static: true }) myElement!: ElementRef;`
- { static: true } - The element/component is available immediately after ngOnInit(). Use when the queried element is not inside an *ngIf, *ngFor, or other structural directive.
- { static: false }  - The element/component becomes available after ngAfterViewInit(). Use when the element is inside a structural directive (e.g. *ngIf, *ngFor).
----
### 📌 Question 88: How do you pass data between components?

#### ✅ Answer:
- Data sharing between components is a fundamental concept that allows components to interact. Depending on the relationship between components.
-  Parent => child = `@Input`
-  child => Parent = `@Output`
- Sibling Components = Shared Service with `Subject/BehaviorSubject`
- Unrelated Components = Shared Service or `NgRx/Signals (Angular 17+)`
----
### 📌 Question 89: How do you implement HTTP in Angular?

#### ✅ Answer:
- Angular provides a built-in **HTTP client module** (HttpClient) to make HTTP requests to back-end APIs. 
- It supports **GET, POST, PUT, DELETE, PATCH**, and more — all based on Observables (RxJS).

----
### 📌 Question 90 : Why is the node_modules folder important?

#### ✅ Answer:

| Reason                       | Description |
|------------------------------|-------------|
| 📚 **Contains Dependencies** | Stores all packages defined in `package.json` (like Angular, RxJS, TypeScript, etc.). |
| 🔗 **Handles Nested Dependencies** | Installs not just direct dependencies but also their own dependencies recursively. |
| 🧱 **Needed to Run & Build** | The Angular CLI, TypeScript compiler, and build tools rely on the code within `node_modules`. |
| 🧪 **Development Tools** | Tools like Jest, Karma, ESLint, and TypeScript are executed from this folder. |
| 🔧 **Required for IDE Support** | Features like IntelliSense, autocompletion, and linting in your IDE depend on libraries from `node_modules`. |

----
### 📌 Question 91 : What is package.json and package-lock.json?

#### ✅ Answer:
- **package.json** - Defines the project metadata, dependencies, and scripts. It's the main configuration file for your project
- **package-lock.json** - The package-lock.json file locks the exact version of every installed package (including sub-dependencies), ensuring consistent installs across environments.
----
### 📌 Question 92 : What is TypeScript?

#### ✅ Answer:
- TypeScript is an open-source superset of JavaScript developed by Microsoft. 
- It adds static typing and other powerful features to JavaScript, making it more suitable for large-scale, enterprise-level applications — such as Angular projects.
----
### 📌 Question 93 : What is Node.js?

#### ✅ Answer:
- **Node.js** is a **runtime environment** that allows you to run **JavaScript on the server side** — outside of a browser. 
- It is built on **Chrome’s V8 JavaScript engine** and is used to create **fast, scalable, and lightweight backend services**.
----
### 📌 Question 94 : What is NPM?

#### ✅ Answer:
- NPM stands for Node Package Manager — it is the default package manager for Node.js.
- It helps you install, manage, and share reusable JavaScript code packages (called modules or dependencies) for your projects
----
### 📌 Question 95 : What is content projection in Angular?

#### ✅ Answer:
- Content Projection in Angular is a powerful feature that allows you to insert external or dynamic content into a component’s template using the <ng-content> directive.

- It enables you to build reusable, flexible components where the parent decides what content goes inside the child.
----
### 📌 Question 96 : When would you use content projection?

#### ✅ Answer:
- You would use Content Projection when you want to create a reusable, flexible, and dynamic UI component that allows the parent component to inject content into it.

----
### 📌 Question 98 : Explain content projection slots in Angular.

#### ✅ Answer:
- Content Projection Slots in Angular allow you to insert multiple different pieces of content into specific placeholders inside a component — by using <ng-content> with a select attribute.

- This is called multi-slot content projection and is useful when you want to project different sections of content (like header, body, footer) into specific places within a component.


----
### 📌 Question 99 : What is module fedration

#### ✅ Answer:
- Module Federation is a feature introduced in Webpack 5 that allows multiple independently built and deployed applications (called micro frontends) to share code at runtime — including components, libraries, or entire features.

- In short, it enables you to dynamically load code from another application without rebuilding or redeploying the host app.


----

### 📌 Question 100 : How angular application works index to main.ts to app-module

#### ✅ Answer:

    index.html
      ⬇
    <app-root>
      ⬇
    main.ts (bootstraps AppModule)
      ⬇
    AppModule (declares AppComponent)
      ⬇
    AppComponent (renders HTML + children)
----




