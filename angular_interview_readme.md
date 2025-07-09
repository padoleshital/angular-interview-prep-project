# 📘 Angular Interview Preparation Documentation
---

## 1. Introduction to Angular

Angular is a TypeScript-based open-source front-end web application framework developed by Google. It is used to build single-page applications (SPA).

> 🔹 Version: Angular 2+ (not AngularJS)  
> 🔹 Written in: TypeScript

---

## 2. Angular Architecture

Angular applications are built using:

- **Modules** (NgModules)
- **Components**
- **Templates**
- **Services**
- **Dependency Injection**

---

## 3. Core Concepts

- **Component**: Basic UI building block (HTML + TS + CSS)
- **Module**: Organizes components and services
- **Template**: HTML + Angular syntax
- **Service**: Logic shared across components
- **Data Binding**: Interpolation, Property binding, Event binding, Two-way binding

---

## 4. Component Lifecycle

Lifecycle hooks:

1. `ngOnInit()`
2. `ngOnChanges()`
3. `ngDoCheck()`
4. `ngAfterViewInit()`
5. `ngOnDestroy()`

---

## 5. Services & Dependency Injection

- Create services using `@Injectable()`
- Inject services into components using constructor
- Singleton pattern

---

## 6. Routing & Navigation

- `RouterModule`
- `RouterOutlet`
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

