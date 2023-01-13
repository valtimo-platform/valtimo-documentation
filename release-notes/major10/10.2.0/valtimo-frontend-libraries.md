# Frontend libraries 10.2.0

## New Features

The following features were added:

* **Notificaties API plugin added to @valtimo/plugin**

  The Notificaties API plugin has been added and supports plugin configuration.

* **Current user Form-io custom component**

  A custom form-io component has been added that provides the Valtimo user profile as form input.
  
* **Form flow - store submission data when moving to the previous step**

  A user now gets the option to save changes in the form when the user clicks the button to go to the previous step in
  the form flow.

* **Introducing a new case tab 'Notes'**

  A new case tab `Notes` has been added which brings the following functionalities:
  - Add a new note to a case.
  - A view of all the notes that have been added to a case.

  Currently, it's not possible to delete or update a note.

* **Moved Audit time**

  The audit time is now displayed next to the date.

* **Modified audit trail dots**

  The audit trail dots are now all the same color. 

* **Plant a tree button**

  There is now a button in the sidebar under the logout button that sends an e-mail to request ritense to plant a tree.

* **Editing case list columns**

  On the admin page of a case type, a tab 'List' is now available. On this tab, case list columns for this case type can
  be added, modified, and re-ordered.

## Bugfixes

The following bugs were fixed:

* **caseassignee dropdown breaks when user has no lastname in keycloak**

  When a user has been configured in keycloak without a lastname, the dropdown of the caseassignee breaks. A check as been added to handle users without a lastname.

* **Custom case header not working if canHaveAssignee is disabled**

  The custom header was only working if the setting `canHaveAssignee` was enabled in the case settings. A fix has been applied to make the custom case header also work without this setting enabled.

* **Connector configuration shows wrong configuration**

  The popup to edit a connector configuration properties, sometimes showed the properties of another connector. This has
  been fixed.

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