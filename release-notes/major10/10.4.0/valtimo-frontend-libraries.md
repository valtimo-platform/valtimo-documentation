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

* **Add configuration component for the 'Create Natuurlijk Persoon Zaakrol' plugin action**

  The 'Create Natuurlijk Persoon Zaakrol' plugin action under the Zaken API plugin now includes a front-end
  configuration component.

* **Use new endpoint to retrieve documents from the Zaken API**

  When `uploadProvider` is set to `UploadProvider.DOCUMENTEN_API` in the environment file, a custom documents page is
  displayed under the documents tab on a case detail page. The documents displayed in the table on this page are now
  retrieved using a Zaken API plugin configuration, by using the new endpoint included in this release:

  `${this.valtimoEndpointUri}v1/zaken-api/document/${documentId}/files`


## Bugfixes

The following bugs were fixed:

* **Fix task modal scroll**

  Fixed an issue where task modals could not scroll when the task form was larger than the vertical size of the screen.

* **AssigneeFilter reset when opening case list**

  Fixed an issue where the wrong assigneeFilter is active and displaying the wrong case list because of it.

* **Fix IBM Carbon accent colors**

  Fixed an issue where Carbon button and tag components were not themed with the Ritense blue theme colors, but with the
  stock IBM blue instead. Refer to [this file](https://github.com/valtimo-platform/valtimo-frontend-libraries/blob/development/projects/valtimo/components/assets/css/carbon.scss)
  if you want to customize theme colors in your implementation. Includes your custom theme file at the end of the
  `styles` array in your implementation's `angular.json` instead of `carbon.scss` exported from `@valtimo/components`.

* **Fix case list URL parameters**

  Query parameters in the URL on the case list page (concerning pagination and search) were retained when navigating to
  other pages inside the application. This issue has been resolved.

## Breaking changes

The following breaking changes were introduced:

* **Moved ZaakInstanceLinkService**
  In `valtimo-backend-libraries`, the `ZaakInstanceLinkService` class has been moved and is now part of
  the [Zaken API module](/introduction/modules/modules.md#zaken-api)

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
