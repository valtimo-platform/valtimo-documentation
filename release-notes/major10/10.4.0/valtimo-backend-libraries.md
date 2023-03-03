# Backend libraries 10.4.0

## New Features

The following features were added:

* **Added Correlation Service ProcessBean**

  This process bean allows exposes methods that provide message correlation and association to a document
which can be used in message throw events as an expression.
More detail [here](/using-valtimo/process/correlating-messages.md).

## Bugfixes

No bugfixes.

## Breaking changes

The following breaking changes were introduced:

* **Deleted process 'Retrieve Document and link to Zaak'**

  The BPMN process 'Retrieve Document and link to Zaak' was deleted. However, applications might still have the
  processes available in the process list. If so, any process links must be moved to the process
  'process-portaaltaak-uploaded-documents'.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

No new deprecations.

## Known issues

No new known issues.
