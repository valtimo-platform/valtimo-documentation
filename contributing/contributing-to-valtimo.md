# Contributing to Valtimo

## Adding a feature or bugfix to Valtimo

1. Create an issue in the [Valtimo](https://github.com/valtimo-platform/valtimo-issues) or [GZAC](https://github.com/generiekzaakafhandelcomponent/gzac-issues) issues repository. 
2. Implement the feature/bugfix in the library repository/repositories and [create a pull request (PR)](#creating-a-pull-request). No reviewers are necessary.
   * Instructions on how to run Valtimo locally can be found in the README.md of the library repositories.
3. Write release notes and documentation for the feature. See below for instructions on how to do this.
4. Merge the PR after getting an approval from the Valtimo team.

## Adding documentation to Valtimo

There are two different circumstances for which documentation for Valtimo can be written. Either because it is related
to a particular change in the product that will be included in an upcoming release, or to add something to the
documentation that is not related to an upcoming release (e.g. fixing spelling errors, or documenting part of an
already existing feature).

* The source of the Valtimo documentation is [this repository](https://github.com/valtimo-platform/valtimo-documentation).
* Information on what language to use, as well as general guidelines can be found [here](style-guide).
* If new pages are added, these should also be added to `SUMMARY.md`. The sidebar shown on the Valtimo documentation corresponds to
  this structure.

### Writing documentation related to an upcoming release

1. Write documentation/release notes and [create a pull request (PR)](#creating-a-pull-request).
   * Use the same base- and target branch as the changes in the library: 
     * `next-minor` for non-breaking changes
     * `next-major` for breaking changes.
2. Merge the PR after getting an approval from the Valtimo team.

### Writing documentation unrelated to an upcoming release

1. In case of a new page, discuss the documentation you want to write with someone from the Valtimo team.
2. Write documentation and [create a pull request (PR)](#creating-a-pull-request).
   * Use `next-minor` as base- and target branch.
3. Merge the PR after getting an approval from the Valtimo team.

## Creating a pull request
For both changes to the library and the documentation, it is required to fork the repository to implement the changes and create the PR.
More information can be found [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).
