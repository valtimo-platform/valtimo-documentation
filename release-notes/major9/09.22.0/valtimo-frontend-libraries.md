# Frontend libraries 5.11.0 (RC)

## New Features

The following features were added:

* **New Documenten API Form.IO upload component**

  A new custom Form.IO component has been added to upload on file at a time, with a modal to input metadata for the
  Documenten API. The component can be inserted into a Form.IO form after following [these instructions](/using-valtimo/upload/upload-to-documenten-api-with-metadata.md).
  When configuring the component in the form builder, various metadata inputs can be given a default value, or be disabled.

## Bugfixes

The following bugs were fixed:

* **Removed the retry in the HttpInterceptor**

  Before the interceptor would always retry an API call if it failed previously.
  This functionality has been removed since it could break applications when timeout (504) errors where being thrown.

* **Assign user in task subscription not destroyed**

  Everytime when the API for getting the list of Valtimo users in a task was loading, it would keep loading even if the task was already completed.
  The subscription is now properly killed and if the task is already completed the API won't be loading anymore.

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
