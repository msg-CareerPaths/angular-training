# Angular Training Introduction

## Description

The following content might be quite detailed. However, we kindly ask that you read it carefully.

This roadmap/training serves as an introduction to the Angular Framework, consisting of several steps. In each step, you will explore a set of theoretical concepts, supported by reference documentation, book chapters, tutorials, and videos.

In parallel, a simple application —an Online Shop— will be built using the concepts learned. After exploring the learning material for each step, either new functionality will be added to the application or existing functionality will be refactored.

## Working Mode

All code written must be published on GitHub.

- You will be provided with a repository in the GitHub organization. Ensure you have access to it.
- **Before starting work**, [create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `feature branch` from the `main` branch. Use a descriptive name for the branch (e.g., chapter-5-components).
- Implement the online-shop requirements from that chapter in your `feature branch`. Commits must be pushed when each individual chapter is finished.
- **In order to request a code review from the mentors**, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `feature branch` to the `main` branch. Notify the mentors about the PR.
- **Once the Pull Request is approved** by the mentors, merge it into the `main` branch.
- Ensure your local `main` branch is up-to-date by pulling the latest changes (git pull).
- For the next chapter, repeat the process by creating a new `feature branch` from the updated `main` branch.
- Keep repeating this process until the training is completed.

## Environment Setup

On your local machine install the following:

- You need to install [NodeJS](https://nodejs.org/en/) (LTS recommended).
- You will need an IDE (Integrated Development Environment) to write and manage your code.
  - [VSCode](https://code.visualstudio.com/download)
  - [Webstorm](https://www.jetbrains.com/webstorm/) as an alternative to VSCode. You can use your student license for it, otherwise you can use the 30 days trial.
- You need to have [Git](https://git-scm.com) installed on your computer.

## Online Shop

You will create a basic online shop that will showcase the functionalities of the Angular framework, building the front-end on top of the backend implemented during the Spring Training.
The application will allow users to browse a catalog of products. It will support the following functional requirements:

- Listing products
- Adding a new product
- Updating an existing product
- Deleting a product

The online shop will also have a "shopping cart" functionality:

- The user can add items to the cart
- The user can increment and decrement the quantity of each product or even remove a product completely from the cart
- Lastly, he can check out the cart and place an order (resulting in the creation of an order in the backend)

### UI Design

Mockups describing the user interface structure can be found in the [mockups](../mockups/mockups.pdf) folder.
These mockups should be used as a guideline, but improvements or deviations from them is allowed.

## Notes

- If you find any link broken, **please** inform your mentor to give you an alternative.
- Try to speed up the videos to _1.5x/2x_ if you find them too slow.

## Timeline

This timeline is just for guidance, take time to understand the concepts before moving on.

- **Week 1**: Chapter 0, Chapter 1, Chapter 2, Chapter 3, Chapter 4, **Open a Pull Request with the project initialization**
- **Week 2**: Chapter 5, **Open a Pull Request**, Chapter 6, **Open a Pull Request**
- **Week 3**: Chapter 7, **Open a Pull Request**, Chapter 8, **Open a Pull Request**
- **Week 4**: Chapter 9, **Open a Pull Request**, Chapter 10, **Open a Pull Request**, **Prepare for Demo**

## Mentions

This section is dedicated to the open source contributors we have used when creating the tutorial, and we want to acknowledge for their educational content.

- [Fireship](https://www.youtube.com/@Fireship) for most of the videos in the training.
- [WebDevSimplified](https://www.youtube.com/@WebDevSimplified)
- [TheNewBoston](https://www.youtube.com/user/thenewboston)
- [Angular Team](https://angular.io)
- [JetBrains](https://www.youtube.com/@JetBrainsTV)
- [VSCode](https://www.youtube.com/@code)
- All other authors of the various links used
