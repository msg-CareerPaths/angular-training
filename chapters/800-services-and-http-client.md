# 8. Services and the HTTP Client [3h]

**Goal:** practice with Angular HttpClient by connecting your frontend with the backend server

## Important Note

Recall the previous chapter material regarding `Observables` and unsubscribing them.

## Mandatory Materials

**Videos**

1. [Angular HTTP Client Quick Start](https://www.youtube.com/watch?v=_05v0mrNLh0)

**Reading**

- [Quick start guide](https://blog.angular-university.io/angular-http/)
- [Angular Http Tutorial](https://www.tutorialspoint.com/angular6/angular6_http_client.htm)
- [Official docs](https://angular.io/guide/http)
- [Environment Files](https://angular.io/guide/build)

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
│       ├── modules
│           ├── shopping-cart
│               ├── services
│                   ├── shopping-cart.service.ts
│.......<the previous files>................................
```


## Further Resources (Optional):

- [Http error handling](https://angular.io/guide/http#error-handling)
- [CORS: Proxy-ing a backend server](https://angular.io/guide/build#proxying-to-a-backend-server)
- [HTTP Interceptor](https://ultimatecourses.com/blog/intro-to-angular-http-interceptors)