# Frontend libraries 11.0.0

## New Features

The following features were added:

* **Angular and dependency upgrades**

  Angular has been upgraded from version 14 to 16. In addition, various dependencies have been upgraded with their
  versions now locked. Please refer to the [migration guide](./migration.md) for instructions on how to upgrade your
  implementation to be compatible with this version of the front-end libraries.

* **Policy Based Access Control**
  
  Implemented PBAC frontend integration for the following features:
  - Assigning an user to a Case
  - Claiming a Case
  - Adding a Case Note
  - Editing a Case Note
  - Deleting a Case Note

  For more information on how to use access control in the front-end, refer to [this page](/using-valtimo/access-control/frontend-access-control.md).

* **Migration of old design components**

  The library `@valtimo/user-interface` has been removed. All of its components have been moved to `@valtimo/components`.
  In order to migrate, please refer to the [migration guide](./migration.md).

* **Placeholders for plugin configuration fields**

  Placeholders are added for plugin configuration fields, so it's more clear what formats are expected for urls.

## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Removed several admin menu items**
  Several admin menu items have been removed:
  - The 'Form-links' page has now been removed in favor of the new 'Process links' page.
  - The 'Contexts' page has been removed. Valtimo no longer supports contexts.
  - The 'Users' page has now been removed.
  - The 'Entitlements' page has now been removed in favor of the new 'Access control' page.

* **Removed case 'Entitlements'**
  The case management page no longer has the option to set the entitlements. This has been replaced by the new 'Access
  control' page.

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
