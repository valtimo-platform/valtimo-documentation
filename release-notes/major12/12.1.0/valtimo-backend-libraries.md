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

* **Toggle for assigning users based on username rather than ID**
  
  A new application property was introduced to configure whether username or ID should be used to assign users to tasks
  or cases. When left unspecified, ID will be used. To help with this, a new value can be defined in permissions, 
  `${currentUserIdentifier}`. This takes into account what the application property has been set to.

  More information can be found [here](/getting-started/modules/core/contract.md#configuration)

* **Access control on dashboards**

  The dashboard feature now supports access control. Permissions can be configured to view dashboards, e.g. based on the dashboard key. More information can be found [here](/reference/modules/authorization.md).

## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.