# 8. Services and the HTTP Client [3h]

**Goal:** practice with Angular HttpClient by connecting your frontend with the backend server

## Important Note

Recall the previous chapter material regarding `Observables` and unsubscribing them.

## Mandatory Materials

**Videos**

1. [Angular HTTP Client Quick Start](https://www.youtube.com/watch?v=_05v0mrNLh0)

**Reading**

- [HttpClient Quickstart guide](https://blog.angular-university.io/angular-http/)
- [HttpClient Tutorial](https://www.tutorialspoint.com/angular6/angular6_http_client.htm)
- [Official docs](https://angular.dev/guide/http)
- [Environment Files](https://angular.dev/tools/cli/environments)

## Online Shop:

> Run `ng generate environments` to create the necessary files in `src/environments`, where you will specify the API base URL.
>
> In `src/environments/environment.ts`, add a property called `apiUrl` and set its value to the API base URL.
>
> Use HttpClient to fetch the products from the backend and populate the product list. (Hint: use the API base URL for the service.)
>
> When navigating to the product detail page, fetch the product information from the backend.
>
> Add a "Delete" button on the detail page that calls the backend to remove the product from the catalog.
>
> Add a "Checkout" button on the shopping cart page that creates a new order on the backend.

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

- [Http error handling](https://angular.dev/guide/http/making-requests#handling-request-failure)
- [CORS: Proxying a backend server](https://angular.dev/tools/cli/serve#proxying-to-a-backend-server)
- [Interceptors](https://angular.dev/guide/http/interceptors)
