# OPT-1. Internationalization

## Introduction

Translating the UI into multiple languages is often an afterthought — until it isn't. Angular ships a first-party story (`@angular/localize`, compile-time), but it is heavy for a small project: separate build targets per locale, per-locale deployments, and more tooling than a learning codebase needs.

This chapter uses **[ngx-translate](https://ngx-translate.org)** instead. It is a runtime library: translations live in JSON files, you switch locale with one call, and no extra build step is needed. It is the easiest way to get a bilingual Online Shop working.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- Why you'd pick runtime i18n (ngx-translate) over compile-time i18n (`@angular/localize`) for a small app — trade-off is bundle size vs. build complexity.
- How ngx-translate loads translation JSON files via `HttpClient`.
- How the `translate` pipe and the `TranslateService` render a translated string.
- How to switch languages at runtime (`translate.use('ro')`).
- Where parameter interpolation and pluralization fit in.

### Practice

Translate all labels, headings, titles, and buttons of the Online Shop into **English** and **Romanian** using ngx-translate.

> Install the packages:
>
> ```bash
> npm install @ngx-translate/core @ngx-translate/http-loader
> ```
>
> Create `src/assets/i18n/en.json` and `src/assets/i18n/ro.json` with the same keys (e.g. `products.title`, `cart.checkout`, `forms.price.required`).
>
> Wire ngx-translate in `app.config.ts`:
>
> ```ts
> provideHttpClient(),
> importProvidersFrom(
>   TranslateModule.forRoot({
>     fallbackLang: 'en',
>     loader: {
>       provide: TranslateLoader,
>       useFactory: (http: HttpClient) =>
>         new TranslateHttpLoader(http, './assets/i18n/', '.json'),
>       deps: [HttpClient],
>     },
>   }),
> ),
> ```
>
> Use the `translate` pipe in templates:
>
> ```html
> <h1>{{ 'products.title' | translate }}</h1>
> <button>{{ 'cart.checkout' | translate }}</button>
> ```
>
> Add a small language switcher (two buttons or a `<select>`) that calls `translateService.use('en' | 'ro')`.
>
> Persist the chosen language in `localStorage` so it survives reloads.

#### Rules

- Translation keys use dot-separated namespaces (`feature.element`), not raw English text — so a label change in one language doesn't break the key.
- Keep `en.json` and `ro.json` structurally identical. If one has a key, both do — even if the Romanian value is still a draft.
- Import `TranslateModule` (or the `TranslatePipe` standalone import) in every component that uses the pipe.

## Mandatory Materials

**Reading**

- [ngx-translate — getting started](https://ngx-translate.org/getting-started/installation/)
- [ngx-translate — translating your components](https://ngx-translate.org/getting-started/translating-your-components/)
- [ngx-translate on GitHub (readme)](https://github.com/ngx-translate/core) — scan for the current API shape.

## Testing

> Pick one presentational component you've translated. Add a test that:
>
> - Provides an in-memory `TranslateLoader` stub returning `{ 'products.title': 'Products' }` for `en` and `{ 'products.title': 'Produse' }` for `ro`.
> - Calls `translate.use('en')`, renders the component, asserts the English text.
> - Calls `translate.use('ro')`, triggers change detection, asserts the Romanian text.

## Optional Resources

### Runtime vs Compile-time i18n

| Dimension                    | ngx-translate (runtime)         | `@angular/localize` (compile-time) |
| ---------------------------- | ------------------------------- | ---------------------------------- |
| Translation storage          | JSON files, loaded via HTTP     | XLF / XMB files, inlined at build  |
| Switch language              | `translate.use('ro')`           | Rebuild + redeploy per locale      |
| Bundle                       | One bundle, all locales lazy    | One bundle per locale              |
| Pluralization / ICU          | Plugin (`messageformat`)        | Built-in ICU                       |
| Best for                     | Small apps, learning, SPAs      | Large apps, SEO per locale         |

### Further Reading

- [ngx-translate — language switching](https://ngx-translate.org/recipes/switching-language/)
- [ngx-translate — ICU / messageformat plugin](https://github.com/lephyrus/ngx-translate-messageformat-compiler) for pluralization.
- [Angular `@angular/localize`](https://angular.dev/guide/i18n) — the first-party alternative, worth knowing exists for larger apps.
- [How to use i18n in Angular](https://www.digitalocean.com/community/tutorials/angular-internationalization)
