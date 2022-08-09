# Backend libraries 9.18.0 RC

## New Features

The following features were added:

* **Added support for custom FormFieldDataresolvers.**

  Introducing support for creating ExternalFormFieldResolvers that implement a new support(String name) method.
  The goal is to let implementation teams define their own FormFieldDataResolvers outside the `ExternalFormFieldType`
  enum definition.

  Form keys should be able to define a key like so `anyDataSource.propertyName`.

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

  FormFieldDataResolver `supports(externalFormFieldType: ExternalFormFieldType)` was deprecated and is replaced with 
  `supports(externalFormFieldType: String)`.

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
