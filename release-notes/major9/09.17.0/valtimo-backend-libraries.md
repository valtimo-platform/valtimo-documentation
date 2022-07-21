# Backend libraries

## New Features

The following features were added:

* **Improved DocumentVariableDelegateImpl**

  The `findValueByJsonPointer` method of the `DocumentVariableDelegateImpl` class
  now returns a collection of elements instead of throwing an exception
  when the node is an ArrayNode.


* **Postgres support**

  Almost all modules within Valtimo now have support for Postgres databases. The exceptions are:
  - `form-flow-valtimo`
  
  Information on how to use Postgres can be found [here](/valtimo-implementation/database-support.md).


* **New feature3**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.


## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

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
