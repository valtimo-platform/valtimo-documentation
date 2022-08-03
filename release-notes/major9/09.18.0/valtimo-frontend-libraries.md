# Frontend libraries 5.6.0 RC

## New Features

The following features were added:

* **Show full name of user in the top bar**

  The full name of the logged-in user can now be shown in the top bar. To enables this features, set
  `showUserNameInTopBar` to true under `featureToggles` in your environment file.

* **Modify and delete plugin configurations**

  On the plugin management page plugin configurations can now be modified and/or deleted from a modal window, 
  after clicking on edit next to an existing plugin configuration.

* **Support multiple ZGW API implementations**

  The libraries `@valtimo/plugin`, '@valtimo/plugin-management' and `@valtimo/user-interface` have been modified to
  support multiple implementations for each ZGW API. For now, an authentication plugin configuration can be selected
  under the Documenten API plugin. The existing OpenZaak plugin code has been refactored to serve as an authentication
  plugin. Associated changes:
  * Process link screen now shows the plugin names with configuration titles for clarity.
  * The `PluginManagementService` and associated models have been moved to `@valtimo/plugin` from
    `@valtimo/plugin-management`, to support using its methods inside plugins.
  * Added a `digitOnly` input directive to `@valtimo/user-interface`, now used for a RSIN input field.

## Bugfixes

The following bugs were fixed:

* **Downgraded `@ng-bootstrap/ng-bootstrap` dependency**

  Recently the dependency `@ng-bootstrap/ng-bootstrap` was upgraded to major version 12 throughout the libraries. This
  caused problems in implementations, as it requires version 5 of Bootstrap, and the libraries use version 4.
  [`@ng-bootstrap/ng-bootstrap` version 11 is compatible with Bootstrap version 4 and Angular 13.](https://www.npmjs.com/package/@ng-bootstrap/ng-bootstrap)

* **Locked `swagger-ui` dependency version**

  The dependency `swagger-ui` was upgrading to `4.13.0`, which was causing issues in implementations. The version has
  now been locked to version `4.12.0`.

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
