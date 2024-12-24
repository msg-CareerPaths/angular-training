# 7. Routing [3h]

**Goal:** understand the basics of Angular Routing and add routing to your project

## Important Note

### Observables

From this point on, you will likely be working with something called `Observables`, which are provided by a library called [RxJs](https://rxjs.dev).

- Observables represent a continuous stream of data that you can subscribe to in order to get data.
- Keep in mind that since Observables are asynchronous, events do not happen in a strict, line-by-line order.
- **IMPORTANT!** Don't forget to unsubscribe from Observables to avoid memory leaks.
  - [Unsubscribe from RxJs Observables](https://www.thisdot.co/blog/best-practices-for-managing-rxjs-subscriptions)
- [Observables vs Promises](https://www.syncfusion.com/blogs/post/angular-promises-versus-observables.aspx)

## Mandatory Materials

**Videos**

1. [Angular Router - The Basics](https://www.youtube.com/watch?v=Np3ULAMqwNo)

**Reading**

- [Angular Routing](https://angular.dev/guide/routing/common-router-tasks)
- Routing tutorial
  - [Enable Routing](https://angular.dev/tutorials/learn-angular/12-enable-routing)
  - [Define a Route](https://angular.dev/tutorials/learn-angular/13-define-a-route)
  - [Use RouterLink](https://angular.dev/tutorials/learn-angular/14-routerLink)
- [First App: Routing](https://angular.dev/tutorials/first-app/10-routing)
- [Routing with Observables: Accessing query parameters and fragments](https://angular.io/guide/router#accessing-query-parameters-and-fragments)

## Online Shop:

> Add routing to your project and implement navigation between the product list, the shopping cart and the product detail page. Use `<router-outlet>` as a placeholder for the currently displayed component in your app.
>
> Set up routing parameters to allow navigation to a specific product's detail page. Hint: Use `snapshot` to capture the product's ID from the navigation parameters and display the corresponding details on the details page.
>
> Add functionality to the icon buttons next to each product in the product list, enabling users to navigate directly to a product’s detail page.
>
> Redirect users from the default path ('/') to the '/products' page, displaying the list of all products by default.
>
> Allow users to navigate to the shopping cart page from the product list by clicking the previously added shopping-cart icon button

### Folder Structure

```text
├── src/app
│   ├── app-routing.module
│   ....<the previous files>................................
```
