# OPT-3. E2E Testing

## Introduction

Unit tests live inside each chapter now (see the **Testing** section in every mandatory chapter). **End-to-end tests** are different: they drive a real browser against a real app and check that user-visible flows work. This chapter adds Cypress to the Online Shop and covers one happy-path scenario.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What E2E testing checks that unit and integration tests can't.
- How Cypress drives a browser, selects elements, and makes assertions.
- Why E2E tests should be few and focused on critical flows.

### Practice

> Write at least one end-to-end test for the following flow:
> - The user opens the app.
> - The app redirects to login.
> - The user logs in with valid admin credentials.
> - The app redirects to the product page.
> - The product list shows at least one product.
> - The user clicks on a product.
> - The product detail page shows that product.

## Mandatory Materials

**Videos**

1. [Cypress E2E Testing](https://www.youtube.com/watch?v=7N63cMKosIE)

**Reading**

- [Introduction to E2E Testing](https://testing-angular.com/end-to-end-testing/#end-to-end-testing)
- [Cypress and Angular — getting started](https://medium.com/angular-in-depth/get-started-with-cypress-d6ac4b910605)
- [Getting started with Cypress](https://docs.cypress.io/app/get-started/install-cypress)

## Testing

> *This whole chapter is about testing.* The Cypress spec above is the deliverable.

## Optional Resources

- [Cypress best practices](https://docs.cypress.io/guides/references/best-practices)
- [Playwright](https://playwright.dev) — an alternative to Cypress worth knowing exists.
