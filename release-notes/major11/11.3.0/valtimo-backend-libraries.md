# Backend libraries 11.3.0

## New Features

The following features were added:

* **RemovalOperations in JsonDocumentContent**
  
  When building a JsonDocument, pre-patches can now include removal operations.

* **Verzoek data mapping to a process variable**

  The Verzoek plugin now provides the ability to map the verzoek data directly to a process variable by adding a `pv` prefix to the chosen `target` on a specified copy strategy.

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
