# Backend libraries 10.5.0

## New Features

The following features were added:

* **Added Correlation Service ProcessBean**

  This process bean allows exposes methods that provide message correlation and association to a document
  which can be used in message throw events as an expression.
  More detail [here](/using-valtimo/process/correlating-messages.md).

## Bugfixes

The following bugs were fixed:

* **Duplicate results when retrieving process instance variables**

  Retrieving process instance variables via the `/v1/process-instance/{id}/variables` endpoint or the underlying
  `getProcessInstanceVariables` method in `CamundaProcessService` would fail if there were multiple variables found
  with the same key.

* **Remove correlation with no business key**

  * Removed methods that allowed sending messages without business key.
  * Changed methods with business key as optional to required

## Breaking changes

The following breaking changes were introduced:

* **Deleted process 'Retrieve Document and link to Zaak'**

  The BPMN process 'Retrieve Document and link to Zaak' was deleted. However, applications might still have the
  processes available in the process list. If so, any process links must be moved to the process
  'process-portaaltaak-uploaded-documents'.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **Deprecation1**

  X was deprecated and is replaced with Y.

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
