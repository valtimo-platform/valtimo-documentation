# Frontend libraries 11.2.0

## New Features

The following features were added:

* **Added option for custom process variable name to download document plugin action in documentAPI**

  Added option for custom process variable name to download document plugin action in documentAPI so you have the option to choose a custom process variable name.
  When left empty the default name is: "resourceId"

* **Export case definitions**

  On the case admin detail page, export functionality is now available in the top right corner. This exports the case
  definition and its related configurations.

* **Switch document definition versions**

  On the case admin detail page, a dropdown is now shown, which allows the user to switch the document definition version
  currently displayed. The selected version affects the version that is exported when the export button is clicked, and
  the version of the document definition that is downloaded when the download button is clicked.

* **Display document definition in Monaco editor**

  The document definition displayed on the admin case detail page is now displayed using the Monaco editor in read-only
  mode.

* **Edit plugin configuration ID**

  The plugin configuration ID can now be edited in the plugin configuration management screens.

* **Prefilling forms with data from the Zaken API**

  Formio forms can now be prefilled with data from the Zaken API. See
  [this page](/reference/modules/form.md#external-data-types) for more information.

* **Show process version on progress tab**

  The version of the process is now visible on the 'Progress' tab of a case.

* **Updates to the Carbon look and feel**

  The following components have been updated to the Carbon library:
    - Case Definition Search Fields tab
    - Case Definition List tab
    - Plugin list

* **Processes Tab**

  The Connected Processes list has been moved and migrated to the ValtimoCarbonList from the Configuration tab and has been added to a new *Processes* of its own.

* **Connected processes to a Document Definition Version**

  Now a process can be connected to a specific version of a Case Definition.

## Bugfixes

The following bugs were fixed:

* **Clear Form.IO token on logout**

  To make Form.IO work correctly, a token is saved in the browser's local storage under the key `formioToken`. This
  local storage entry is now cleared on closing the Form.IO component and on closing the browser.

* **No `null` while loading menu items**

  Previously, while menu items in the left sidebar were loading, they would show `null`. This issue has been resolved.

* **Added permission check on 'Go to case' link**

  A permission check has been added so that the 'Go to case' link inside the task list no longer result in an
  unauthorized-error.

* **Added permission check on case-list**

  Permission checks have been added to the case-list to avoid an unauthorized-error when clicking on a case.

* **Added permission check on 'Create New Case' button**

  A permission check has been added to the 'Create New Case' button, so that it can no longer result in an
  unauthorized-error.

* **Send along timezone offset with every HTTP request**

  All HTTP request sent from the client now include a `X-Timezone-Offset` header, which contains the user's timezone
  offset (compared to UTC). The back-end libraries now use this offset to return the correct results when searching cases by date.

* **Slow loading of notes**

  The loading of the case notes could take a long time depending on the access control settings. This has been solved.

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