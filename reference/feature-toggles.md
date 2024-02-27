# Feature toggles

Sometimes, different features in implementations need to be switched on or off. This could be because a feature
is (not) needed, or a feature is currently in development and is switched off by default, enabling the release chain to
continue uninhibited.

Below is an overview of available feature toggles for Valtimo, with a short description of their function.

## Front-end

In the frontend, feature toggles can be configured under the `featureToggles` key in the Angular environment file(s)
with a `boolean` value.

* **`applicationTitleAsSuffix`**

  By default, the application title is shown in the browser tab as a prefix e.g. 'Valtimo - Processes'.
  With this featureToggle it is possible to change this to 'Processes - Valtimo'.

* **`disableFormFlow`**

  By default, it is assumed the `form-flow` module is configured in the backend, and thus a form flow option is
  available on the Process links admin page. If this module is not configured, use this toggle to disable the option on
  the Process links page.

* **`showUserNameInTopBar`**

  If enabled, the full name of the user currently logged in is shown in the top bar next to the user menu button.

* **`experimentalDmnEditing`**

  If enabled, it is possible to edit DMN tables from the ui from the admin page. This feature is experimental, please
  refer to [the release notes](../release-notes/major9/09.20.0/valtimo-frontend-libraries.md) for known issues.

* **`caseSearchFields`**

  If enabled, a non-functional demo version of case search fields will replace the search sidebar on the case list page.

* **`disableCaseCount`**

  If set to `true`, showing the number of open cases in the menu is disabled.

* **`caseListColumn`**

  If enabled, the column list tab will be shown on the case management page.

* **`showPlantATreeButton`**

  If enabled, a 'Plant a tree' button will appear in the right sidebar.

* **`sortFilesByDate`**

  If enabled, files under the documents tab on a case detail page will be sorted by date in descending order.

* **`largeLogoMargin`**

  If enabled, the logo on the left in the top bar will have a large margin around it. This works well for logo's that
  are bigger horizontally than they are vertically.

* **`returnToLastUrlAfterTokenExpiration`**

  If enabled, the user will be returned to the page they were last on before they were automatically logged out after
  their refresh token expired.

* **`enableObjectManagement`**

  If enabled, a new menuitem 'objects' will appear in the left sidebar menu. This menu item can have one or more submenu
  items depending on the configuration. For more information [here](/getting-started/modules/zgw/object-management.md)

* **`hideValtimoVersionsForNonAdmins`**

  If enabled, the Valtimo version information in the right sidebar will only be visible for admins and will be hidden
  for any other users.