# Backend libraries 12.3.0

## New Features

The following features were added:

* **Added support for updating the submission data inside a Form Flow SpEL expressions**

  A Form flow SpEL expressions now accepts updating the submission data.
  See [this page](/using-valtimo/form-flow/create-form-flow-definition.md#expressions) for more information.

* **Added filtering for zaakinformatieobjecttypes**

  Zaakinformatieobjectypes (document types) are now filtered on three properties:
  * concept
    * Only types that are not in concept will be returned
  * beginGeldigheid
    * Only types with a beginGeldigheid in the past are returned
  * eindeGeldigheid
    * Only types with an empty or future eindeGeldigheid are returned

## Bugfixes

The following bugs were fixed:

* **Form flow data is now correct when navigating back and forward**

  The data that a user entered in the form of a form flow is now correctly saved and displayed again when
  navigating back and forward in a form flow.

  If the user makes changes in a previous step, any later step will now either show correct data, or not show any data
  at all.

* **Form flow spamming Submit button**

  A double click on the Submit button in a form flow will now properly go to the next step and not to any step further
  than that.

* **Form IO Data Grid and Edit Grid are now prefilled correctly**

  When a form is opened the show a Data Grid or Edit Grid, the form will now only fill the fields that should be
  prefilled.


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

* **Form flow - form data can disappear when making a change in a previous step**

  When a user goes back to the form of a previous step. Makes changes. Then goes to the next step again, the form might
  miss some of the data that the user did enter before going back. This has been done intentionally and only happens
  when new data submitted in a previous steps can affect existing data in later steps.

* **Issue2**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue
