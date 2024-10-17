# Contributing to Valtimo

## Adding a feature or bugfix to Valtimo

1. Create an issue in the [Valtimo](https://github.com/valtimo-platform/valtimo-issues) or [GZAC](https://github.com/generiekzaakafhandelcomponent/gzac-issues) issues repository.
2. Tag the Product Owner in the Github issue. A member of the product team will be in touch to discuss the issue and the proposed solution.
   * The Github handle of the Product Owner can be found in the README.md of the issue repositories.
3. Implement the feature/bugfix in the library repository/repositories and [create a pull request (PR)](https://docs.valtimo.nl/contributing/contributing-to-valtimo#creating-a-pull-request). No reviewers are necessary.
   * Instructions on how to run Valtimo locally can be found in the README.md of the library repositories.
4. Write release notes and documentation for the feature. See below for instructions on how to do this.
5. Merge the PR after getting an approval from the Valtimo team.

## Adding documentation to Valtimo

There are two different circumstances for which documentation for Valtimo can be written. Either because it is related to a particular change in the product that will be included in an upcoming release, or to add something to the documentation that is not related to an upcoming release (e.g. fixing spelling errors, or documenting part of an already existing feature).

## Writing documentation related to an upcoming release

1. Write documentation/release notes. These should be written as a PR for [this repository](https://github.com/valtimo-platform/valtimo-documentation). There should already be a branch for the upcoming Valtimo release (e.g. `feature/release-notes-9.17.0`). Make a branch from that branch, and do not forget to merge it back into that Valtimo release branch as part of the PR, add all [team Valtimo developers](https://github.com/orgs/valtimo-platform/teams/valtimo-product-team/members) to this PR as reviewers.
   * Information on what language to use, as well as general guidelines can be found [here](../contributing/style-guide/).
   * Release notes to in the `release-notes` package.
   * If new pages are added, these should also be added to `SUMMARY.md`. The sidebar shown on GitBook corresponds to this structure.
2. Merge the branch after getting an approval from the Valtimo team.

## Writing documentation unrelated to an upcoming release

1. In case of a new page, discuss the documentation you want to write with someone from the Valtimo team.
2. Write documentation. This should be written as a PR for [this repository](https://github.com/valtimo-platform/valtimo-documentation). Make a branch from the `main` branch, add all [team Valtimo developers](https://github.com/orgs/valtimo-platform/teams/valtimo-product-team/members) to this PR as reviewers.
3. Merge the branch after getting an approval from the Valtimo team.
