# Frontend libraries 11.2.0

## New Features

The following features were added:

* **Added option for custom process variable name to download document plugin action in documentAPI**

  Added option for custom process variable name to download document plugin action in documentAPI so you have the option to choose a custom process variable name.
  When left empty the default name is: "resourceId"

* **Export case definitions**

  On the case admin detail page, export functionality is now available in the top right corner. This exports the case
  definition and its related configurations.

## Bugfixes

The following bugs were fixed:

* **Clear Form.IO token on logout**

  To make Form.IO work correctly, a token is saved in the browser's local storage under the key `formioToken`. This
  local storage entry is now cleared on closing the Form.IO component and on closing the browser.

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
