# Backend libraries 9.19.0 (RC)

## New Features

The following features were added:

* **Filter out plugin configurations without actions**

  The REST endpoint `GET /api/plugin/configuration` now supports a new request parameter
  called `includeActionless` which expects a boolean value.
  When the parameter is `false` the endpoint will only return plugin configurations that 
  have 1 or more actions.
  Example: `GET /api/plugin/configuration?includeActionless=false`

  The default value of this new request parameter is `true`.

* **New feature2**

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
