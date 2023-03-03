# Backend libraries 10.4.0

## New Features

The following features were added:

No features.

## Bugfixes

No bugfixes.

## Breaking changes

The following breaking changes were introduced:

* **Deleted process 'Retrieve Document and link to Zaak'**

  The BPMN process 'Retrieve Document and link to Zaak' was deleted. However, applications might still have the
  processes available in the process list. If so, any process links must be moved to the process
  'process-portaaltaak-uploaded-documents'.

* **Moved ZaakInstanceLinkService**
  In `valtimo-backend-libraries`, the `ZaakInstanceLinkService` class has been moved and is now part of
  the [Zaken API module](/introduction/modules/modules.md#zaken-api)

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

No new deprecations.

## Known issues

No new known issues.
