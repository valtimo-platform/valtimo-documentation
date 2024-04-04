# Frontend libraries 12.0.0

## New Features

The following features were added:

* **Translation management**

  An administrator can now configure and override translations from a front-end admin page. For more information on how
  to configure and use this, [refer to this page](/using-valtimo/localization/configuring-localization.md).

* **Form flow management**

  An administrator can now see, create and edit form flows from a front-end admin page. For more information on form
  flows, refer to [this page](/using-valtimo/form-flow/create-form-flow-definition.md).

* **Inline edit document definition**

  Document definition can now be edited inline to create a new version.

* **Pending changes modal extension**

  The pending changes modal has been extended to accept custom modals. An example of this use would be a pending changes modal for an 'Edit mode' function, where you might want to have three buttons (e.g. *Keep editing*, *Save*, *Discard*) instead of the two buttons that are offered out of the box.

  More details about the PendingChangesComponent can be found [here](/using-valtimo/pending-changes/pending-changes.md)

* **Creating document definitions via the admin interface**

  A document definition can now be created via the admin interface. This is an alternative to creating a document
  definition in the project, which enables the user to create a document definition without needing to create a file in
  the project.

  More details about creating document definitions can be found [here](/using-valtimo/document/create-document-definition.md)

* **Zaken-api plugin action start and end Hersteltermijn**

  A Zaken-API plugin action has been added for both starting and ending a recovery period.

  More information about the plugin actions can be
  found [here](/using-valtimo/plugin/zaken-api/configure-zaken-api-plugin.md#start-recovery-period).

* **New Zaak type link endpoint**
  The document Zaaktype link configuration now uses the `/api/management/v1/zgw/zaaktype` endpoint.
  This new endpoint requires a zaken-api plugin to be configured.

* **Document object type selection is now conditional**
  When connecting a zaak to the document, the document object type selection is now only shown when using the OPEN_ZAAK upload-provider.

* **Configurable colors for internal case statuses**
  When configuring an internal case status, you are provided with a fixed list of colors. This colors are in accordance to the Carbon Design System
  and will help differentiate between different satuses you might create.

* **Zaken-api plugin action create, update and delete zaakeigenschap**
  A Zaken-API plugin action has been added for creating, updating and for deleting a zaakeigenschap. More information
  about the plugin actions can be
  found [here](/using-valtimo/plugin/zaken-api/configure-zaken-api-plugin.md#create-zaakeigenschap).

* **form-link to process-link**
  The library `@valtimo/form-link` has been renamed to `@valtimo/process-link`. For information on how to migrate, refer
  to [this page](migration.md).

* **Override Form.io options**

  Options used by Form.io in the renderer can now be modified by using the following key in your environment file:
  `formioOptions`. Refer to [this page](/reference/environment.md) for more information.

* **Verzoek plugin JSON mapping**

  The verzoek plugin can now be configured so that the entire verzoek data is copied to a target location. For
  information on how to configure the verzoek plugin, refer
  to [this page](/using-valtimo/plugin/verzoek/configure-verzoek-plugin.md).

* **Show readable process errors**

  When a user models and deploys an erroneous BPMN process, the user will now get a readable and useful error message.

* **Documenten API plugin version**

  To determine the available features of the Documenten API, the plugin can now be configured with the version of the Documenten API that is used. This version is
  also shown on all Case definition management pages that use the Documenten API plugin. For more
  information on how to configure the verzoek plugin, refer
  to [this page](/using-valtimo/plugin/documenten-api/configure-documenten-api-plugin.md)

## Bugfixes

The following bugs were fixed:

* **Not all case definitions are visible in the menu**

  The left sidebar did not show all case definitions when there were more than 10. Now the left sidebar will show all
  case definitions.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **ChoiceFieldModule**

  The ChoicefieldModule has been removed. Also the ChoiceFieldService and a few models have been moved to the *@valtimo/components* library.
  Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

* **OpenZaakModule**

  The OpenZaakModule has been removed. EmailExtensionComponent has been removed altogether. The OpenZaakTypeLinkExtension has been moved to *@valtimo/plugin*
  under the ZakenApiPluginModule. Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

* **Changes to feature toggle**
  - `enableTabManagement` is now enabled (`true`) by default.
  - `caseListColumn` is now enabled (`true`) by default.
  - `enableObjectManagement` is now enabled (`true`) by default.
  - `caseSearchFields` has been removed as it was not used.
  - `disableFormFlow` has been removed. Form flow is always enabled from now on.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **ContactMomentModule**

  Contact-moment has been deprecated and will be replaced with plugins in the future.

* **CustomerModule**

  Customer has been deprecated and will be replaced with plugins in the future.

* **ConnectorManagementModule**

  Connector-management has been deprecated and replaced by plugins.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Issue1**
    * Discovered in version x.x.x
    * Describe what can be done to work around the issue

* **Issue2**
    * Discovered in version x.x.x
    * Describe what can be done to work around the issue
