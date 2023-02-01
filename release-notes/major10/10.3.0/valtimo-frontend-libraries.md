# Frontend libraries 10.3.0

## New Features

The following features were added:

* **Trigger search when hitting Enter key**

  When one of the search fields has been filled in and I press 'Enter', the search is executed

* **Added process key to process started and ended audit events**

  Process started and process ended events in the audit trail now show the associated process name.

* **Link to change password page**

  A password reset link is shown in the 'account' tab in the right sidebar.

* **Added Portaaltaak plugin**

  Portaaltaak plugin module is added to @valtimo/plugin which supports plugin configuration.

* **Added Duplicate button to Forms**

  A button has been added to duplicate the form that is currently being edited

* **Business logic for fieldtype/datatype/searchtype combinations**

  On the case-management page the "Match" field is hidden and is only shown for fields of data type text, any other field uses "Exact". 
  The range option is not available for fields of data type "Yes / no" in case-management.
  If a number field has the value '0', the search form can be submitted in the cases page.

* **Resizable Carbon sidenav**

  The sidenav included in the Carbon design system does not include resize functionality. This functionality is now
  included by default on desktop resolutions. The default, minimum, and maximum sizes of the sidenav can be configured
  under the `customLeftSidebar` property in the environment file(s). The size is saved in the local storage, so the user
  preference will be retained on refresh.

* **Improved styling of Beagle/Bootstrap elements**

  The Carbon design system resets styling and replaces it with its own. This broke the look and feel of various elements
  throughout the product, including Form.IO forms. The compatibility between Carbon and Beagle/Bootstrap has been
  improved in this release.

* **Added new Portaaltaak plugin**

  This plugin makes it possible for valtimo to manage tasks in the Objecten API.

* **Added dropdown list to case search**

  It is now possible to use a multiselect dropdown or a single select dropdown when searching to cases. This can be
  configured in the admin menu. More information [here](../../../using-valtimo/document/configuring-search-fields.md).

## Bugfixes

The following bugs were fixed:

* **Unable to switch process versions on 'Process links' page**

  Fixed an issue where the process diagram didn't update after selecting the process version on the process links page.

* **Added role support to sidenav**

  After migrating to the Carbon design system in major 10, adding menu items based on the roles of the logged-in user
  was accidentally removed. This feature has been added again. A logged-in user will only see the menu items which they
  can access with their roles.

* **Continue case search after error**

  When searching for cases led to an HTTP error on the case list page, search after this would not be executed.
  This has been fixed. Errors are handled gracefully and subsequent valid search are executed.

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
