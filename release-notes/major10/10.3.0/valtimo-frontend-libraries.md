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

* **Add ability to override feedback menu item to trigger a mailTo**

  The menu item `feedback` in the right sidebar is currently linked to `https://www.valtimo.nl/feedback/`. 
  An environment property `overrideFeedbackMenuItemToMailTo` is added to be able to override the default and use mailTo instead.
  The subject and the body of this email are set in the translation files to support multiple languages.

  An example of a full configuration:
  ``` 
  {
    email: '',
    subjectTranslationKey: 'subject',
    bodyTranslationKey: 'body'
  }
  ```

## Bugfixes

The following bugs were fixed:

* **Unable to switch process versions on 'Process links' page**

  Fixed an issue where the process diagram didn't update after selecting the process version on the process links page.

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
