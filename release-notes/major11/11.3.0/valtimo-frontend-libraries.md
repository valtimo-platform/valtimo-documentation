# Frontend libraries 11.3.0

## New Features

The following features were added:

* **Support for value resolvers to set date in `Create Zaakbesluit` plug-in action configuration**
    
    It is now possible to use process variable or document json path to set `Starting date` and `Expiration date` in `Create Zaakbesluit` plug-in action configuration so that each besluit has its own start and expiration date.

## Bugfixes

The following bugs were fixed:

* **Exporting permissions did not include the `roleKey` property**

  The `roleKey` property was not included when exporting the permissions for a role. Because of this, it could not be imported or be used for auto-deployment.

* **Plug-in action configuration can be completed without filling mandatory field**

  `Create Zaakbesluit` plug-in action configuration can be completed without filling mandatory `Starting date` field.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
