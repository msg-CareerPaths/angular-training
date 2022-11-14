## Working Mode (Must-Read)

The road-map consists of several steps. In each step, a set of theoretical concepts are explored, supported by reference documentation, book chapters, tutorials and videos. In parallel, a simple application will be built with the learned concepts: the *Online Shop* application.

After the learning material for a given step was sufficiently explored, either some new functionality will be added to this application or old functionality will be refactored.

All the code written must be published on GitHub. Access [this link](https://classroom.github.com/a/xWWQ0td5) to create your own repository.
Commits must be pushed when each individual chapter is finished. [Create](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository) a `develop` branch from the `master` branch **before starting work**.

**In order to request a code review from the trainers**, you must [open a pull request](https://help.github.com/en/articles/creating-a-pull-request) from the `develop` to the `master` branch. Inform them in your **daily standup** of this or through a PM.
**Once the Pull Request is approved** by the trainers, merge it into master and create another branch from master to continue work.
*Repeat ad infinitum* (until training end's)

## Environment

You can work using your local environment:
- You need to install [NodeJS](https://nodejs.org/en/) and [VSCode](https://code.visualstudio.com/download).
- You can use [Webstorm](https://www.jetbrains.com/webstorm/) as an alternative to VSCode
- You need to have [Git](https://git-scm.com) installed on your computer. Have a look at [this video](https://www.youtube.com/watch?v=HkdAHXoRtos) for a quick crash course.

In the `backend` folder you can find a server-side implementation for the online shop. To run this server perform the following:
- Open the `backend` folder in your terminal
- `npm ci` (only needed the first time your run the server)
- `npm start`
- Open [http://localhost:3000](http://localhost:3000) in your browser.

## Online Shop
The application will simply browse through a catalog of products. It will support:

- Listing the products,
- Adding a new product,
- Updating an existing product,
- Deleting a product.

The online shop has a "shopping cart" functionality:
- The user may add items into the cart,
- He may increment and decrement the quantity of each product or even remove a product completely from the cart,
- Lastly, he can check out the cart and place an order (resulting in the creation of an order in the backend).

Mockups describing the user interface structure can be found in the [mockup's](./mockups/mockups.pdf) folder.
These mockups should be used as a guideline, but improvements or deviations from them is allowed.

### Notes:
- If you find any link broken, **please** inform your mentor to give you an alternative.
- Try to speed up the videos to *1.5x/2x* if you find them too slow.
- Try to connect to the Backend from the Spring Training if you have training completed (you might need to change the port for your requests)

## Timeline
This timeline is just for guidance, take time to understand the concepts before moving on.

- **Day 1**: Chapter 0, Chapter 1, Chapter 2
- **Day 2**: Chapter 3, Chapter 4, **Open a Pull Request**
- **Day 3**: Fix Review Remarks => Merge to Master => Create a new branch, Chapter 5, Chapter 6
- **Day 4**: Chapter 7, Chapter 8, **Open a Pull Request**
- **Day 5**: Catchup & Optional Chapters
