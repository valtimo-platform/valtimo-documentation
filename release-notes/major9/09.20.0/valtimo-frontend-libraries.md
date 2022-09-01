# Frontend libraries 5.9.0 (RC)

## New Features

The following features were added:

## Bugfixes

The following bugs were fixed:

* **Progress tab selectedProcessInstanceId not set if processDocumentInstances is empty**

  The progress tab was assuming that there was at least one process started and tried to set the following property `selectedProcessInstanceId`.
  In cases that there was no process started it would throw an error in the console. This has been fixed and an empty 
  state has been added to show the user no process has been started yet.

## Breaking changes

No known breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
