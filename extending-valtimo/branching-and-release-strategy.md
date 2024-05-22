# Branching and release strategy

The Valtimo product aims to deliver features to its user quickly. Contributions from outside the core
development team are welcomed. To make this possible, the below branching and release strategy is used.

## Branching

### `next-minor`

Both [valtimo-frontend-libraries](https://github.com/valtimo-platform/valtimo-frontend-libraries) and [valtimo-backend-libraries](https://github.com/valtimo-platform/valtimo-backend-libraries/)
are mainly developed in one single branch: `next-minor`. As its name implies, all commits made into `next-minor` will be
released publicly when the next minor version of the product is released.

### `next-major`

Breaking changes for the product are developed in the `next-major` branch. Only changes related to the breaking change
are made here. Unrelated changes are still committed to `next-minor`.

While in development, `next-minor` is frequently merged into `next-major`.

Once the breaking changes in `next-major` are finished and tested, `next-major` is merged into `next-minor`. This
commit is tagged and released. Work then continues in the `next-minor` branch until a new breaking change needs to be
made, and a new `next-major` branch is created.

### Back-end libraries

Because of security reasons, back-end features are developed in feature branches, branched off from `next-minor`. 
Feature branches are named `feature/*`. Parts of the feature are developed in branches prefixed with `story/`,
which include a story number. For example: `story/12345-add-endpoint`. These story branches are merged into
the feature branch as soon as possible. In addition, `next-minor` is merged frequently into the feature branch.

Bugfix branches follow the naming scheme: `bugfix/12345-fix-security`. They are either merged into `next-minor`, 
`feature/*` or to `next-major` (if this exists). 

### Front-end libraries

All branches for the front-end libraries are branched from `next-minor` or `next-major` (if this exists).

Since the front-end does not have the same security concerns as the back-end libraries, it is recommended to develop new
features behind feature toggles. During development, the toggle can be enabled on the test environment, while remaining
disabled in production. When the feature is done, the feature toggle is removed and the feature is made available to all.

In some cases, feature branches like explained above for the back-end libraries, can also be used for the front-end
libraries. For this reason, branches for parts of a feature behind a feature toggle, are prefixed with `story/`, for
example: `story/12345-add-button`. The naming scheme `feature/*` is reserved for longer lived feature branches.

If the use case calls for it, feature toggles can be retained if a feature is finished, for example if the feature
needs to be turned off by default.

## Releasing

Changes in `next-minor` in both `valtimo-frontend-libraries` and `valtimo-backend-libraries` are released as frequently
as possible, but only when the branches are stable. There is a maximum of 4 weeks between releases.

A release is done by tagging the commit that is to be released. After this, a short-lived release branch is created,
from which a release candidate is made for internal testing. If this release is satisfactory, a release is made based
on the release tag.

### Bugfixes

If bugs are encountered for unreleased minor or major versions, fixes for these bugs are made in `bugfix/*` branches,
branched of from `next-minor` and `next-major` respectively.

If bugs need to be fixed in previous releases, the fixes are done in `next-minor` if it all possible. After the fixes
are tested and merged, they are cherry-picked into a branch based of the tags of the release(s) in which they need to be
fixed. Afterward, a new patch release is made with the fix included. As a rule of thumb, bugs are only fixed in the last
minor release, in order to avoid maintaining many releases at once.

An example scenario for a bugfix in a previous release:

`next-minor` is currently headed for release 12.4. A bug has been encountered in release 12.3. In this case,
the fix for this bug is developed in the branch `bugfix/12345-fix-issue`, based of the `next-minor` branch. After
`bugfix/12345-fix-issue` is merged into `next-minor`, the merge commit is cherry-picked into a branch made from the
`12.3` release tag. A release is made from this branch with the fix included, and the latest commit of this branch is
tagged as `12.3.1`. The release is branch is deleted.

With this way of working, bugfixes are always included in the next minor release. If another issue is encountered in
`12.3.1`, the same process is followed, and a `12.3.2` release is made, based off the `12.3.1` release tag.




