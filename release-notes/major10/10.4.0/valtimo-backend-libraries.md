# Backend libraries 10.4.0

## New Features

The following features were added:

* **Added Correlation Service ProcessBean**

  This process bean allows exposes methods that provide message correlation and association to a document
which can be used in message throw events as an expression.
More detail [here](/using-valtimo/process/correlating-messages.md).


* **Object management**

  For the object management you need a configured objectsApiPlugin and a configured objectTypesApi.
  
  The object management uses the objectapi plugin to get objects from the objects api and uses the objectTypesApi plugin to get the version and the uuid of the validate the object or to get all objects form that object type

  The object management module is only available in the ZGW version of Valtimo.

  The object management uses the search module to show values of the retried objects in a list. It also uses the search module to configure search fields where you can search within the objects you want to retrieve.


## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Deleted process 'Retrieve Document and link to Zaak'**

  The BPMN process 'Retrieve Document and link to Zaak' was deleted. However, applications might still have the
  processes available in the process list. If so, any process links must be moved to the process
  'process-portaaltaak-uploaded-documents'.

* **Breaking change2**

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
