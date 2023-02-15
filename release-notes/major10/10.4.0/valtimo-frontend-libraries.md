# Frontend libraries 10.4.0

## New Features

The following features were added:

* **Add configuration component for 'Create Portal Task' plugin action**

  When the Portal Task plugin is configured, the plugin action 'Create Portal Task' can now be linked to a BPMN user
  task on the process links page.

* **Add configuration component for 'Create Zaak' plugin action**

  When the Zaken API plugin is configured, the plugin action 'Create Zaak' can now be linked to a BPMN service
  task on the process links page.

* **Add configuration component for the 'Verzoek' plugin**

  The 'Verzoek' plugin can now be configured from the plugin management page. To support the adding of multiple Verzoek
  types, a new component has been added to the `@valtimo/user-interface` library: `v-multi-input-form`. This component
  allows the input of a template containing a `v-form` component, and allows multiple instances of this specified form
  template within another `v-form` component.

## Bugfixes

The following bugs were fixed:

* **Fix task modal scroll**

  Fixed an issue where task modals could not scroll when the task form was larger than the vertical size of the screen.

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
