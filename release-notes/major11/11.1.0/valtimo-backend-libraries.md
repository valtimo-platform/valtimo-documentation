# Backend libraries 11.1.0

## New Features

The following features were added:

* **Form.io forms targetKey property**

  Form.io forms in Valtimo now support a `targetKey` property. This property defines a location to which the submitted
  form values should be stored.

## Bugfixes

The following bugs were fixed:

* **Fix DMN upload**

  The `/v1/process/definition/deployment` endpoint only accepted uploaded files with the .bpmn extension, causing DMN uploads to fail.

## Breaking changes

No breaking changes.

## Deprecations

The following was deprecated:

* **Task comments**

  Task comments have been deprecated and will be removed in a future Valtimo version.

## Known issues

No known issues.
