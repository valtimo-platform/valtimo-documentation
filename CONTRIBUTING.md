# Contributing to Valtimo

## Adding a feature or bugfix to Valtimo

1. Discuss the (approach for the) feature or bugfix with someone from the Valtimo team. This is to reduce the work that
   is required, as it can both reduce the chances of feedback and allows for the Valtimo team to provide some pointers
   on how to proceed. It is not necessary to do this for smaller bugfixes.
2. Create a story in the Valtimo backlog and and tag it with impl team.
3. Implement the feature/bugfix and create a PR to the development branch. Add all team Valtimo developers to this PR
   as reviewers (see here for the list of developers).
4. Write release notes and documentation for the feature. See below for instructions on how to do this.
5. Merge the branch after getting an approval from the Valtimo team.

## Adding documentation to Valtimo

There are two different circumstances for which documentation for Valtimo can be written. Either because it is related
to a particular change in the product that will be included in an upcoming release, or to add something to the
documentation that is not related to an upcoming release (e.g. fixing spelling errors, or documenting part of an
already existing feature).

## Writing documentation related to an upcoming release

1. Write documentation/release notes. These should be written as a PR for this repository. There should already be a
   branch for the upcoming Valtimo release (e.g. `feature/release-notes-9.17.0`). Make a branch from that branch, and
   do not forget to merge it back into that Valtimo release branch as part of the PR, and include all developers to the
   PR as reviewers.
   - Information on what language to use, as well as general guidelines can be found [here](STYLE-GUIDE.md).
   - Release notes to in the `release-notes` package.
   - If new pages are added, these should also be added to `SUMMARY.md`. The sidebar shown on GitBook corresponds to
      this structure.
2. Merge the branch after getting an approval from the Valtimo team.

## Writing documentation unrelated to an upcoming release

1. In case of a new page, discuss the documentation you want to write with someone from the Valtimo team.
2. Write documentation. This should be written as a PR for this repository. Make a branch from the `main` branch, and
   include all developers to the PR as reviewers.
3. Merge the branch after getting an approval from the Valtimo team.
