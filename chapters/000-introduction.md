# Angular Training Introduction

## Description

First, I would like to start by emphasizing with reader that the following read is quite verbose, but I would like to ask that you read the following carefully.

This is a roadmap/training for a introduction into the Angular Framework consisting of several steps.
In each step, a set of theoretical concepts are explored, supported by reference documentation, book chapters, tutorials and videos.

In parallel, a simple application will be built with the learned concepts: the _Online Shop_ application.
After the learning material for a given step was sufficiently explored either some new functionality will be added to this application or old functionality will be refactored.

## Working Mode

All the code written must be published on GitHub.

- Create a repository on your personal GitHub account and grant access to your mentors. (Be sure to specify your name if your username is weird).
- Commits must be pushed when each individual chapter is finished.
- [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from the `main` branch **before starting work**.
- **In order to request a code review from the mentors**, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `main` branch. Add the mentors as reviewers.
- **Once the Pull Request is approved** by the mentors, merge it into `main` and create another branch from `main` to continue working.
- After merging, delete your `develop` branch. Then, update your `main` branch by pulling the latest changes (git pull).
- Carry on your work by creating another `develop` branch and work on it.
- Keep repeating this process until the training is completed.

## Environment Setup

On your local machine install the following:

- You need to install [NodeJS](https://nodejs.org/en/) (LTS recommended).
- You will need an IDE (Integrated Development Environment) to write and manage your code.
  - [VSCode](https://code.visualstudio.com/download)
  - [Webstorm](https://www.jetbrains.com/webstorm/) as an alternative to VSCode. Note if you are still a student you can use your student license on it, otherwise you can use the 30 days trial.
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
- Try to connect to the Backend from the Spring Training if you have training completed (you might need to change the port for your requests)

## Timeline

This timeline is just for guidance, take time to understand the concepts before moving on.

- **Day 1**: Chapter 0, Chapter 1, Chapter 2, Chapter 3
- **Day 2**: Chapter 4, Chapter 5
- **Day 3**: Chapter 6, **Open a Pull Request**, Fix Review Remarks => Merge to Master => Create a new branch,
- **Day 4**: Chapter 7, Chapter 8
- **Day 5**: Chapter 9, Chapter 10
- **Day 6**: Chapter 11, **Open a Pull Request**, Fix Review Remarks => Merge to Master => Create a new branch
- **Day 7**: Chapter 12
- **Day 8**: Optional Chapters or Fix Review Remarks/Refactor Code

## Mentions

This section is dedicated to the open source contributors we have used when creating the tutorial, and we want to acknowledge for their educational content.

- [Fireship](https://www.youtube.com/@Fireship) for most of the videos in the training.
- [WebDevSimplified](https://www.youtube.com/@WebDevSimplified)
- [TheNewBoston](https://www.youtube.com/user/thenewboston)
- [Angular Team](https://angular.io)
- [JetBrains](https://www.youtube.com/@JetBrainsTV)
- [VSCode](https://www.youtube.com/@code)
- All other authors of the various links used
