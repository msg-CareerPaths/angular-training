# OPT-3. E2E Testing

## Introduction

Unit tests live inside each chapter now (see the **Testing** section in every mandatory chapter). **End-to-end tests** are different: they drive a real browser against a real app and check that user-visible flows work. This chapter adds **Playwright** to the Online Shop and covers one happy-path scenario.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What E2E testing checks that unit and integration tests can't.
- How Playwright drives a browser, selects elements (locators, `getByRole`, `getByTestId`), and makes assertions with auto-waiting.
- Why E2E tests should be few and focused on critical flows.

### Practice

> Install Playwright: `npm init playwright@latest`.
>
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

1. [Playwright in 100 Seconds](https://www.youtube.com/watch?v=Xz6lhEzgI5I)

**Reading**

- [What is End-to-End Testing?](https://bugbug.io/blog/software-testing/what-is-end-to-end-testing) — tool-agnostic intro; focus on the "What is end to end testing?" section and the unit/integration/E2E comparison table. (Skip the vendor recommendations lower down.)
- [Playwright — installation](https://playwright.dev/docs/intro)
- [Writing tests with Playwright](https://playwright.dev/docs/writing-tests)
- [Locators](https://playwright.dev/docs/locators) — the recommended way to pick elements.

## Testing

> *This whole chapter is about testing.* The Playwright spec above is the deliverable.

## Optional Resources

- [Playwright best practices](https://playwright.dev/docs/best-practices)
- [Playwright Test Generator](https://playwright.dev/docs/codegen) — record a flow in the browser and generate the spec.
- [Cypress](https://www.cypress.io) — the other major E2E tool; worth recognizing in older projects. See [Cypress best practices](https://docs.cypress.io/guides/references/best-practices).
