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

* **Zaken-api plugin action end Hersteltermijn**

  A Zaken-API plugin action has been added for ending a recovery period

* **New Zaak type link endpoint**
  The document Zaaktype link configuration now uses the `/api/management/v1/zgw/zaaktype` endpoint.
  This new endpoint requires a zaken-api plugin to be configured.

* **Document object type selection is now conditional**
  When connecting a zaak to the document, the document object type selection is now only shown when using the OPEN_ZAAK upload-provider.

* **Configurable colors for internal case statuses**
  When configuring an internal case status, you are provided with a fixed list of colors. This colors are in accordance to the Carbon Design System
  and will help differentiate between different satuses you might create.

## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

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
