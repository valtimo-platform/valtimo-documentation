# Frontend libraries 5.11.0 (RC)

## New Features

The following features were added:

* **New Documenten API Form.IO upload component**

  A new custom Form.IO component has been added to upload one file at a time, with a modal to input metadata for the
  Documenten API. The component can be inserted into a Form.IO form after following [these instructions](/using-valtimo/upload/upload-to-documenten-api-with-metadata.md).
  When configuring the component in the form builder, various metadata inputs can be given a default value, or be disabled.
  If the component is included in a form for a user task, the user can input metadata for each file upload. These files
  are then registered in the Documenten API on form submission.

* **New date format possible for date columns in the Valtimo lists**

  The `viewType` property for listFields is extended with the option to add set a custom format based on the library that we use `moment.js`.
  Before you would declare a date column as `viewType: 'date'` and now you can add a optional format option like this `viewType: date:DD-MM-YYYY`.
  After the separator `(:)` any `valid moment.js` formatting is allowed. 
  A full list of all the moment.js format options can be [found here](https://momentjscom.readthedocs.io/en/latest/moment/04-displaying/01-format/).

* **Added parameters to the 'ValtimoFormioOptions' class**

  The parameters `readOnly` (boolean), `decimalSeparator` (string) and `thousandsSeparator` (string) are added to the 'ValtimoFormioOptions' class. You can now pass these parameters inside an 'options' object when using the `valtimo-form-io` Angular component.

* **Override default task list tabs**

  A new (optional) environment property `visibleTaskListTabs` is introduced to change the visibility of the default tabs in the `valtimo-task-list` component. 
  The new property is an array which include the tabs that need to be visible on the page. The array can include the following values: `DefaultTab.MINE`, `DefaultTab.OPEN`, and `DefaultTab.ALL`.

  With this new property you can either hide certain tabs that are visible by default or you could change the default order of the tabs.


## Bugfixes

The following bugs were fixed:

* **Removed the retry in the HttpInterceptor**

  Before the interceptor would always retry an API call if it failed previously.
  This functionality has been removed since it could break applications when timeout (504) errors where being thrown.

* **Assign user in task subscription not destroyed**

  Everytime when the API for getting the list of Valtimo users in a task was loading, it would keep loading even if the task was already completed.
  The subscription is now properly killed and if the task is already completed the API won't be loading anymore.

* **Added missing translations for several components**

  The components `summary page`, `taskDetailModal`, and `list component` were missing translations


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
