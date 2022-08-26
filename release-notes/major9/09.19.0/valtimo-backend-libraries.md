# Backend libraries 9.19.0 (RC)

## New Features

The following features were added:

* **New form flow `onBack` property**

  Form flows already supported the `onOpen` and `onComplete` properties. The `onBack` property has been added that is
  triggered when navigating to a previous step. Information on how to use these properties in a form flow can be found
  [here](/using-valtimo/form-flow/create-form-flow-definition.md#expressions).

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.


## Bugfixes

The following bugs were fixed:

* **JdbcProcessFormAssociationRepository insert statement runtime exception**

  Running on an externally hosted Mysql 8.0.15 instance caused unknown column type exceptions with `useServerPrepStmts`. For more information [see](https://github.com/brettwooldridge/HikariCP/wiki/MySQL-Configuration).
  To prevent determining the sql column type now the type is specified.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Form flow `onBack` property is null for existing records**

* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **Deprecation1**

  X was deprecated and is replaced with Y.

* **Deprecation2**

  X was deprecated and is replaced with Y.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Issue1**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue

* **Issue2**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue
