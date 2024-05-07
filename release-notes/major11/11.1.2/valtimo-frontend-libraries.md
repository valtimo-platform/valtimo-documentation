# Frontend libraries 11.1.2

## New Features

No new features.

## Bugfixes

The following bugs were fixed:

* Custom boolean values don't show correctly in the CarbonList

* Output events of custom FormFlow components as described on [this page](/using-valtimo/form-flow/create-custom-component.md)
  were fixed.

* Breadcrumbs work correctly in conjunction with the pending changes modal.

* `valtimo-form-io` now includes a default empty submission, this fixes the ProductAanvragen connector configuration
  form.

* `valtimo-form-io` now renders after the current JWT token is saved in locale storage, so that `token` can be used
 in calculated value fields.

* HTML values are now only escaped once in a form.io input field. For more information on how to interpolate data in Form.io forms, see [Interpolating data in Form.io](/using-valtimo/forms/interpolating-data-in-formio.md).

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
