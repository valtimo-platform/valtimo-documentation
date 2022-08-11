# Backend libraries 9.18.0 RC

## New Features

The following features were added:

* **Added support for custom FormFieldDataResolvers**

  Support was added for creating ExternalFormFieldResolvers that implement a new support(String name) method.
  Previously, an enum `ExternalFormFieldType` denoted the prefixes that were supported, which prevented
  implementations from making custom prefixes. Information on how to use form field data resolvers
  can be found [here](/using-valtimo/form-link/using-form-field-data-resolvers.md), and information on
  how to create custom form field data resolvers can be found [here](/extending-valtimo/form-link/custom-form-field-data-resolver.md).

* **Added new ZGW plugins** 
  * documenten-api
    * This plugin has a connection to the Documenten API. When a document was generated this plugin is used to 
    upload the document to the Documenten API
  * zaken-api
    * This plugin has a connection to the Zaken API. This plugin supports the action to link documents that have been uploaded 
    to the Documenten API to the Zaak of the current case 
## Bugfixes

The following bugs were fixed:

* **'No form linked' when a start form has been linked**

  For some cases, it was no longer possible to manually create a new case because of a popup saying that there was no
  start form configured even though it had been configured. The logs would show an 500 Internal Server Error.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **FormFieldDataResolver supports method**

  FormFieldDataResolver `supports(ExternalFormFieldType externalFormFieldType)` was deprecated and is replaced with 
  `supports(String externalFormFieldType)`.

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
