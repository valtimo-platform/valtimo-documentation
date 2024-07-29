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

* **FormViewModel**

  A new module was added to the backend libraries, `FormViewModel`. More information can be found [here](/extending-valtimo/form-view-model/form-view-model.md).

* **Toggle for assigning users based on username rather than ID**
  
  A new application property was introduced to configure whether username or ID should be used to assign users to tasks
  or cases. When left unspecified, ID will be used. To help with this, a new value can be defined in permissions, 
  `${currentUserIdentifier}`. This takes into account what the application property has been set to.

  More information can be found [here](/getting-started/modules/core/contract.md#configuration)

## Bugfixes

The following bug was fixed:

* **Error when no recipients are present when sending an email**

  When an email is sent by Valtimo, and there are no recipients due to none of the recipients being whitelisted, an
  error would incorrectly occur.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
