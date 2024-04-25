# Backend libraries 11.3.0

## New Features

The following features were added:

* **Verzoek data mapping to a process variable**

  The Verzoek plugin now provides the ability to map the verzoek data directly to a process variable by adding a `pv` prefix to the chosen `target` on a specified copy strategy.

## Bugfixes

The following bugs were fixed:

* **Besluit creation fails because of missing non-mandatory property**

  When `reason for expiry` is not selected while configuring 'Create Zaakbesluit' plugin action in the 'Besluiten API' plug-in, the following error occurs and the besluit creation fails: Cannot force empty String ("") to ` com.ritense.besluitenapi.client.Validation`. It's now fixed.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
