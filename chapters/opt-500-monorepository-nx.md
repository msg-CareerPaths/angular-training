# OPT-5. Mono-Repository with Nx

> ⚠️ **Deprecated:** this optional module is no longer up to date. Kept for reference.

## Introduction

Big teams often put their apps and libraries in a single repository and use a monorepo tool to coordinate builds, dependencies, and testing. **Nx** is the most popular choice in the Angular ecosystem.

## Goal

### Theory

By the end of this chapter you should be able to explain:

- What a monorepo is and the trade-offs vs many-repos.
- What Nx adds on top of a plain monorepo (project graph, affected commands, cached builds).
- How Nx structures apps vs libraries.

### Practice

> Migrate the Online Shop into an Nx workspace:
> - [Migrate your Angular app to Nx](https://nx.dev/migration/migration-angular).
> - [Create an internal library for reusable components](https://nx.dev/node-tutorial/04-create-libs).
> - Move the components from [Opt 4](opt-400-component-library-development.md) into it and consume them from the app.
> - Keep this library private (don't publish unless you want to).

## Mandatory Materials

**Videos**

1. [Nx Quickstart](https://www.youtube.com/watch?v=VUyBY72mwrQ)
2. [How the Pros Scale Huge Software Projects](https://www.youtube.com/watch?v=9iU_IE6vnJ8)

**Reading**

- [What is a monorepo](https://www.perforce.com/blog/vcs/what-monorepo)
- [Nx Workspace](https://nx.dev/getting-started/intro)
- [Nx Mental Model](https://nx.dev/using-nx/mental-model)
- [Nx and Angular](https://nx.dev/getting-started/nx-and-angular)

## Testing

> After the migration, run `nx test` on each project and make sure the tests you already wrote still pass.

## Optional Resources

- [Imposing constraints in the project](https://nx.dev/structure/monorepo-tags)
- [Using Nx at enterprises](https://nx.dev/guides/monorepo-nx-enterprise)
- [Performance profiling](https://nx.dev/guides/performance-profiling)
