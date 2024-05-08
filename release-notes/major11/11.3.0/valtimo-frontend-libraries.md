# Frontend libraries 11.3.0

## New Features

The following features were added:

* **Zaken-api plugin action start and end Hersteltermijn**

  A Zaken-API plugin action has been added for both starting and ending a recovery period.

  More information about the plugin actions can be
  found [here](/using-valtimo/plugin/zaken-api/configure-zaken-api-plugin.md#start-recovery-period).

* **Zaken-api plugin action create, update and delete zaakeigenschap**
  A Zaken-API plugin action has been added for creating, updating and for deleting a zaakeigenschap. More information
  about the plugin actions can be
  found [here](/using-valtimo/plugin/zaken-api/configure-zaken-api-plugin.md#create-zaakeigenschap).

* **Support for value resolvers to set date in `Create Zaakbesluit` plug-in action configuration**

  It is now possible to use process variable or document json path to set `Starting date` and `Expiration date` in `Create Zaakbesluit` plug-in action configuration so that each besluit has its own start and expiration date.

## Bugfixes

The following bugs were fixed:

* **Besluiten API: create Besluit without Vervalreden**

  Creating a Besluit with an empty 'vervalreden' was not possible due to a serialization error.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
