# 0. Angular Training Introduction

## Introduction

Welcome. This training is a guided roadmap into the Angular framework, built around a small application you will write yourself: the **Online Shop**. Each chapter mixes theory (concepts, documentation, videos) with a concrete slice of work on that application.

The read ahead is deliberately verbose — please go through it carefully before starting.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What the training is and how its chapters are structured.
- Which tooling you need installed before you start.
- The *Online Shop* domain you are going to build.
- The working mode (branching, pull requests, code review).

### Practice

> You will set up your environment and your repository here — no application code yet.

#### Rules

All the code written must be published on GitHub.

- Create your own repository on your personal account and give access to your mentor (specify your name if your username is esoteric).
- Commits must be pushed when each individual chapter is finished.
- [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from `main` **before starting work**.
- To request a code review, open a [pull request](https://help.github.com/en/articles/creating-a-pull-request) from `develop` to `main`. Notify your mentor at daily standup or by PM.
- **Once the PR is approved**, merge it into `main`, delete `develop`, pull `main` locally, then create a fresh `develop` and continue.
- Repeat until the training ends.

## Mandatory Materials

**Environment Setup** — install on your local machine:

- [NodeJS](https://nodejs.org/en/) (latest LTS, 22.x or newer at time of writing).
- An IDE:
  - [Webstorm](https://www.jetbrains.com/webstorm/) (Non-Commercial Version), or
  - [VSCode](https://code.visualstudio.com/download).
- [Git](https://git-scm.com).
- [Notepad++](https://notepad-plus-plus.org/downloads/) — convenient plain-text editor.

**Online Shop — Domain**

A very basic online shop showcasing Angular. It will:

- List products,
- Allow adding, updating, and deleting a product.

It has a "shopping cart":

- The user may add items into the cart,
- Increment / decrement quantity, or remove an item,
- Check out the cart and place an order (creating an order on the backend).

**Mock Backend** — instructions at [mock-backend](https://github.com/msg-CareerPaths/mock-backend).

**UI Design** — mockups in the [mockups](../mockups/mockups.pdf) folder. Use them as a guideline; deviations are allowed.

## Testing

> No tests to write in this chapter. From Chapter 5 onward each chapter has a **Testing** section with what to test for that chapter's work. There is no longer a separate "Unit Testing" optional chapter — testing lives alongside the feature that produces it.

## Optional Resources

### Notes

- If any link is broken, ask your mentor for an alternative.
- Videos may reference an **older version** of Angular — read them critically, and prefer this training's modern Angular 22 conventions.
- Playback at *1.5x–2x* if videos feel slow.
- If you also completed the Spring training, try pointing this frontend at that backend (port adjustments may be needed).

### Timeline (guidance only)

- **Day 1**: Chapter 0, 1, 2, 3
- **Day 2**: Chapter 4, 5
- **Day 3**: Chapter 6 — **open a PR**, address review, merge, branch again
- **Day 4**: Chapter 7
- **Day 5**: Chapter 8, 9, 10
- **Day 6**: Chapter 11, 12 — **open a PR**, address review, merge, branch again
- **Day 7**: Chapter 13, 14, 15
- **Day 8**: Optional chapters or review fixes / refactor

### Mentions

- [Angular Team](https://angular.dev)
- [Fireship](https://www.youtube.com/@Fireship) — most of the videos in the training.
- [WebDevSimplified](https://www.youtube.com/@WebDevSimplified)
- [TheNewBoston](https://www.youtube.com/user/thenewboston)
- [Angular University](https://angular-university.io/)
- [LogRocket](https://blog.logrocket.com)
- [Rainer Hahnekamp](https://www.youtube.com/@RainerHahnekamp)
- [Joshua Morony](https://www.youtube.com/@JoshuaMorony)
- [JetBrains](https://www.youtube.com/@JetBrainsTV)
- [VSCode](https://www.youtube.com/@code)

### ZScaler Issues (only when needed)

You may encounter ZScaler issues (company proxy). If you see `SSL CERTIFICATE ERRORS`, `UNABLE TO GET LOCAL ISSUER CERTIFICATE`, or random connection failures, suspect ZScaler.

First steps:

- Download the certificate from the company.
- Save it as `C:\zscaler.crt`.

**Webstorm**

- `File > Settings`, search `Proxy`, enable `Auto-detect proxy settings`.
- Search `Server Certificates`, click `+` in the Accepted Certificates table, add the ZScaler cert.

**Git**

- Open `C:\Users\<your_username>\AppData\Local\Programs\Git\mingw64\ssl\certs\ca-bundle.crt`.
- Open `zscaler.crt` in a second Notepad.
- Append the content of `zscaler.crt` to the end of `ca-bundle.crt` (leave a blank line).
- Or make Git trust the Windows store: `git config --global http.sslBackend schannel`.

**Node.js**

- Search `environment` in the Windows taskbar, open `Edit environment variables...`.
- Under User variables add `NODE_EXTRA_CA_CERTS` pointing at `C:\zscaler.crt`.
- Restart your machine.
