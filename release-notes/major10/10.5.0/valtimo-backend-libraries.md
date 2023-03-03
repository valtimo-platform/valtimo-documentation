# Backend libraries 10.5.0

## New Features

The following features were added:

* **Plugin action: Download document**

  This new plugin action, downloads a document from the Documenten API and stores it in a temporary file. More
  information on this process link can be
  found [here](/using-valtimo/plugin/documenten-api/configure-documenten-api-plugin.md#download-document).

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.


## Bugfixes

The following bugs were fixed:

* **Duplicate results when retrieving process instance variables**

  Retrieving process instance variables via the `/v1/process-instance/{id}/variables` endpoint or the underlying
  `getProcessInstanceVariables` method in `CamundaProcessService` would fail if there were multiple variables found
  with the same key.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

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
