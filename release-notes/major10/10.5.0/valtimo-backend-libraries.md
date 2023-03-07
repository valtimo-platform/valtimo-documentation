# Backend libraries 10.5.0

## New Features

The following features were added:

* **Added Correlation Service ProcessBean**

  This process bean allows exposes methods that provide message correlation and association to a document
  which can be used in message throw events as an expression.
  More detail [here](/using-valtimo/process/correlating-messages.md).

* **Portaaltaak process name change**

  The name for the Portaaltaak system process which, can run when portal task is completed, has been changed to
  `Process completed Portaaltaak`.

## Bugfixes

The following bugs were fixed:

* **Duplicate results when retrieving process instance variables**

  Retrieving process instance variables via the `/v1/process-instance/{id}/variables` endpoint or the underlying
  `getProcessInstanceVariables` method in `CamundaProcessService` would fail if there were multiple variables found
  with the same key.

* **Duplicate file uploads due to form prefill**

  When a file-upload user task was executed multiple times within the same process instance, the subsequent execution
  would prefill the form with previously uploaded files. This caused the file to be duplicated on the case if the
  prefilled file was not removed from the list by the user.
  
  The result data of the upload component will no longer be saved to the document at the specified key. If
  post-processing is needed, this can be implemented by:
  - Customizing the `document-upload` system process (Zaken API, GZAC)
  - Implementing an event listener for `DocumentRelatedFileSubmittedEvent` (Documenten API File upload component)
  - Implementing an event listener for `DocumentRelatedFileSubmittedEvent` (Valtimo File upload component)

* **Bug2**

  Description of what the issue was.

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
