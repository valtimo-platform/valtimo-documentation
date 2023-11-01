# Frontend libraries 11.1.0

## New Features

The following features were added:

* **Improved support for plugin auto-deployment properties placeholders**

  A plugin configuration auto-deployment file now supports:
  - Placeholders that refer to Java system properties.
  - Placeholders inside nested properties.
  - Multiple placeholders in a single field.

* **Added PendingChanges guard and modal to prevent losing unsaved changes**

  Implemented a mechanism for checking wether or not any changes have been made to the current page. If any navigation occurs on these pages, a modal will pop up asking for confirmation in case any unsaved changes exist.

  Instructions on how to set this up can be found [here](/using-valtimo/pending-changes/pending-changes.md).

## Bugfixes

The following bugs were fixed:

* **Data is lost when accidentally navigating back when editing a form**

  When editing a form and navigating to a different page, a modal pops up asking for confirmation.

* **FormIO token refreshes only once**

  When using the **valtimo-form-io** component from *@valtimo/components*, the local storage property *formioToken* gets updated every time the token refreshes after expiring.

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
