# Frontend libraries 12.3.0

## New Features

The following features were added:

* **Form Flow Breadcrumbs**

  When the feature toggle is enabled, users will see a new breadcrumb trail on top of every form flow. This allows a
  user to quickly navigate between the different steps of the form flow.
  See [this page](/using-valtimo/form-flow/create-form-flow-definition.md#breadcrumbs) for more information.

* **Form flow - Going back without validation**

  Added support for going back to a previous form without the need for required fields to be filled in.
  See [this page](/using-valtimo/form-flow/create-form-flow-form.md#going-back-to-the-previous-form) for more
  information.

## Bugfixes

The following bugs were fixed:

*  **Loss of information in URL when opening tasks for a case**

When opening a task for a case, the URL path would get replaced with `/#`.

* **Configured 'multiple case count' widgets not working**

  Configured 'multiple case count' widgets were unable to find the document definition it was configured for.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.