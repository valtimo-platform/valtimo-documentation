# Backend libraries 9.25.0 (RC)

## New Features

The following features were added:

* **Feature toggle: change disabled input fields behaviour**

  Disabled form fields are prefilled and saved by default. This behaviour deviates from the web-standard where disabled
  elements are not included in the submit body.

  It is now possible to toggle this behaviour so that disabled fields will not be prefilled nor saved.

  For more information on using this feature toggle see [this page](/using-valtimo/forms/forms.md).

* **Improved error handling and logging in case of unsupported JWT token**

  A missing or empty email address in the JWT token no longer causes a null pointer exception.

* **Performance improvements when retrieving case definitions**

  The query for retrieving list of case definitions has been improved. Performance increases for this API call have
  improved significantly when dealing with a lot of case definitions or case definition versions. Calls that took 10
  seconds have now been observed to take less than half a second after these improvements.


* **Case search field configuration ordering**

  The order of search fields can now be changed with the existing PUT endpoint. The PUT endpoint now accepts a list of
  search fields from which the order is saved into the database. More information about search fields can be
  found [here](/extending-valtimo/document/search-fields.md).

## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Case search field configuration**

  Some breaking changes have been made regarding the case search field configurations that were introduced in
  Valtimo `9.24.0`.
    * The search field types `datatype`, `searchtype` and `matchtype` have been renamed to use uppercase characters.
      This is a breaking change for several search field API endpoints. The new names are: `dataType`, `searchType`
      and `matchType`. No migration is necessary.
    * The endpoint `PUT /api/v1/document-search/{documentDefinitionName}/fields` now accepts an array of search fields
      instead of a single search field. No migration is necessary.

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

