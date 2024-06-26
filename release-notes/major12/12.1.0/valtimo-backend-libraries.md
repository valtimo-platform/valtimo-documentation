# Backend libraries 12.1.0

## New Features

The following features were added:

* **ZGW document keywords (trefwoorden)**

  Document keywords can now be configured on a case. This will allow the user to add keywords when uploading a file using the Documenten API.
  Autodeployment for this configuration is also available. More information can be found [here](/using-valtimo/zgw/documents/zgw-documents.md#keywords-trefwoorden).

* **ZGW document list column autodeployment**

  Document list columns can now be configured via autodeployment. More information can be found [here](/using-valtimo/zgw/documents/zgw-documents.md#autodeployment-1).

* **Verified form flow submission**

  The submission data is now verified when submitting a form that is part of a form flow.

* **Valueresolver for Zaakresultaat**

  Zaakresultaat information can now be retrieved using the `zaakresultaat` prefix. For example: the `zaakresultaat:omschrijving` expression can be used to prefill a field with the description of the Zaakresultaat in a summary form. More information can be found [here](/reference/modules/value-resolver.md#zgw-value-resolvers).


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
