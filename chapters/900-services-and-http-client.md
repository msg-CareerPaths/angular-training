# 9. Services and the HTTP Client [3h]

**Goal:** practice with Angular HttpClient by connecting your frontend with the backend server

## Important Note

Recall the previous chapter material regarding `Observables` and unsubscribing them.

If you are using signals, consider using the interop methods provided in the reading section.

## Mandatory Materials

**Videos**

1. [Angular HTTP Client Quick Start](https://www.youtube.com/watch?v=_05v0mrNLh0)

**Reading**

- [Quick start guide](https://blog.angular-university.io/angular-http/)
- [Creating a service](https://angular.dev/guide/di/creating-and-using-services)
- [Dependency Injection](https://angular.dev/guide/di)
- [Angular Http](https://angular.dev/guide/http)
- [Environment Files](https://angular.dev/tools/cli/environments)
- [RxJS Interop for Signals](https://angular.dev/ecosystem/rxjs-interop)
- [Dependency Injection explained in Angular](https://blog.logrocket.com/how-dependency-injection-works-in-angular/)
- [Injection Context](https://angular.dev/guide/di/dependency-injection-context)

### Rules

- Mark your services with `@Injectable({providedIn: 'root'})`
- Do

## Online Shop:

The logic you are currently developing should be added to the `container` components.

> Run `ng generate environments` to create in `src/environements` the files where you will specify the API base url 
>
> Make the `src/environments/environment.ts` have a property called `apiUrl` which has a value toward the API base url
>
> Use HttpClient to read the products from the backend to fill in the product list. (Hint: use the api base url for the service)
>
> When navigating to the product detail page, read the product information from the backend.
>
> Add a new "Delete" button on the detail page, which calls the backend to remove a product from the catalogue.
>
> Add a new "Checkout" button on the shopping cart page, which creates a new order on the backend.

### Folder Structure
```text
├── src
│   ├── environments
│       ├── environment.ts
│       ├── environment.development.ts
│   ├── app
│       ├── services
│       │   ├── products.service.ts
│       ├── features
│           ├── shopping-cart
│               ├── services
│                   ├── shopping-cart.service.ts
│.......<the previous files>................................
```


## Further Resources (Optional):

- [Http error handling](https://angular.dev/guide/http/making-requests#handling-request-failure)
- [Proxy-ing to a backend server](https://angular.dev/tools/cli/serve#proxying-to-a-backend-server)
- [HTTP Interceptor](https://angular.dev/guide/http/interceptors)
- [Injection Tokens](https://angular.dev/guide/di/defining-dependency-providers#injection-tokens)