# Frontend libraries 10.8.0

## New Features

The following features were added:

* **IDs added to menu items and search field buttons**

  - The menu item configuration in the Angular environment file now supports an optional 'id' property. When configured, the 'id' property is added to the HTML element.
  - 'id' attributes have been added to the 'clear' and 'search' buttons on the case list page.

* **Added due date configuration to portaaltaak plugin**

  The 'Create Portaaltaak' action of the Portaaltaak plugin now supports the optional 'verloopDurationInDays' field. 
  When this field has been configured, the 'verloopdatum' property of the task object contains the calculated due date. 

## Bugfixes

The following bugs were fixed:

* **Can not upload files from user task**

  A bug that prevented some users from uploading files in a user task has been fixed.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
