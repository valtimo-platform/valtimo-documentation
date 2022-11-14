# Backend libraries 9.25.0 (RC)

## New Features

The following features were added:

* **Feature toggle: change disabled input fields behaviour**

  Disabled form fields are prefilled and saved by default. This behaviour deviates from the web-standard where disabled elements are not included in the submit body.
  
  It is now possible to toggle this behaviour so that disabled fields will not be prefilled nor saved.

  For more information on using this feature toggle see [this page](/using-valtimo/forms/forms.md).

* **Improved error handling and logging in case of unsupported JWT token**

  A missing or empty email address in the JWT token no longer causes nullpointer exceptions. 

* **Performance improvements when retrieving case definitions**

  The query for retrieving list of case definitions has been improved. Performance increases for this API call have
  improved significantly when dealing with a lot of case definitions or case definition versions. Calls that took 10
  seconds have now been observed to take less than half a second after these improvements.


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

