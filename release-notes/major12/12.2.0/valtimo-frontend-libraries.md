# Frontend libraries 12.2.0

## New Features

The following features were added:

* **Dependency upgrades**

  Various dependencies in the libraries have been upgraded for security reasons.

* **Cypress removed from codebase**

  The infrastructure to implement Cypress end-to-end tests has been removed from the front-end libraries codebase,
  since it was never used; integration testing is done using Playwright instead.

* **Value path selector**

  In many configuration forms in the application, manual path inputs are used. For example, an admin fills in
  `case:createdOn` for a search field configuration. A component has now been implemented to allow for the selection
  of possible values for these fields using a dropdown. A manual input option is still available in these places by
  switching a toggle. 

  In this version, this value path selector has been implemented  for configuring task and case search fields, case list
  columns, and for selecting the default value for Form.io components inside the form builder. The latter is available
  under a Valtimo tab in configuration modals for each Form.io component.

## Bugfixes

The following bugs were fixed:

* **Form builder stability**

  On the admin form management page, the form builder sometimes would not allow form components to be saved. This issue
  should be resolved.

* **Custom form.io component not rendering consistently**

  A fix has been implemented for custom Form.io components not rendering correctly in certain situations. To implement
  this fix, please refer to the [migration notes of this release](migration.md).

* **Documenten API metadata modal in Form.io forms**

  The documenten API metadata modal for the Documenten API uploader custom component for Form.io now works properly.


## Known issues

This version has the following known issues:

* **Camera feature for custom Form.io upload components might not work properly**
    * Discovered in version 12.1.0
    * If you encounter this issue, the camera feature can be disabled in the Form.io form configuration.
