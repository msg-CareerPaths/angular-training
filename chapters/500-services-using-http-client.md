## 5. Services using HttpClient [3h]

**Goal:** practice with Angular HttpClient by connecting your frontend with the backend server

#### Required:

*Videos*

1. [Angular HTTP Client Quick Start](https://www.youtube.com/watch?v=_05v0mrNLh0)

*Reading*

- [Quick start guide](https://blog.angular-university.io/angular-http/)
- [Angular Http Tutorial](https://www.tutorialspoint.com/angular6/angular6_http_client.htm)
- [Official docs](https://angular.io/guide/http)

#### Online Shop:

> Use HttpClient to read the products from the backend to fill in the product list.
>
> When navigating to the product detail page, read the product information from the backend.
>
> Add a new "Delete" button on the detail page, which calls the backend to remove a product from the catalogue.
>
> Add a new "Checkout" button on the shopping cart page, which creates a new order on the backend. **Note**: The response of this request may require you to set the `responseType` flag on the HttpClient options parameters as here `this.httpClient.post('/api/orders', data, { responseType: 'text' })`. For more info [check this](https://angular.io/guide/http#requesting-data-from-a-server).

#### Further Resources (Optional):

- [CORS: Proxy-ing a backend server](https://angular.io/guide/build#proxying-to-a-backend-server)
- [Http error handling](https://angular.io/guide/http#error-handling)
- [Unsubscribe from RxJs Observables](https://www.thisdot.co/blog/best-practices-for-managing-rxjs-subscriptions)
    - You can create an abstract class or a [mixin](https://www.typescriptlang.org/docs/handbook/mixins.html) from which you can inherit the functionality to unsubscribe.
