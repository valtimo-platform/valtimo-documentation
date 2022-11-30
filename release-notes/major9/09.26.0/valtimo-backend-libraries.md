# Backend libraries 9.26.0 (RC)

## New Features

The following features were added:

* **Case settings**

  Case settings have been introduced. Settings such as being able to assign a user to a case can be found here.
  Additionally, case settings can be loaded from a file when the corresponding document definition is created. For more
  information on how to create a case definition when a document definition is created, see [here](/using-valtimo/case/creating-case-settings.md).

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.

## Bugfixes

The following bugs were fixed:

* **Enhanced error information on form submission errors**

  When you try to submit a form whose `Document` or `ProcessDocumentDefinition` can't be found, the parameters used to query these entities will be logged/reported back. This is especially useful when you encounter this error on a system that you don't have direct access to.

* **Listing connectors could potentially exhaust the database connection pool**
  
  When requesting a list of connectors, some queries were locking the tables. This could result in an exhausted database connection pool. The transaction settings have been changed to prevent this from happening.

## Breaking changes

The following breaking changes were introduced:

* **Case settings**

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
