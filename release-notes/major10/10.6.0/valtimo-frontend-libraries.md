# Frontend libraries 10.6.0

## New Features

The following features were added:

* **Loading indicator Documenten API documents tab**

  The documents tab shown on a case detail page when Documenten API has been configured as the upload provider, now
  shows loading animations when loading the list of files linked to the case, and when downloading files.

* **Added featureToggle to make the application title a suffix**

  By default, the application title is shown in the browser tab as a prefix e.g. 'Valtimo - Processes'.
  We have added the featureToggle `applicationTitleAsSuffix` to be able to change this to 'Processes - Valtimo' 
  from the environment files.
  
* **Configuration component for the 'Link Document to Besluit' plugin action**

  The 'Link Document to Besluit' plugin action under the Besluiten API plugin now includes a front-end configuration
  component.

* **Configuration components for Catalogi API plugin actions**

  The following Catalogi API plugin actions now have configuration components:
  - Retrieve Statustype
  - Retrieve Resultaattype
  - Retrieve Besluittype

* **Triggering fresh searches every time**

  The search functionality on the case list page has been improved to trigger a search every time, even if the search term has not changed. 
  This change enables users to search seamlessly, even when working with asynchronous data.

* **Case list refactor**

  Over time, much functionality had been added to the case list page. All these elements did not always work
  together properly, nor were they optimal from a user experience perspective. The case list component has been
  refactored with the following points in mind:
  * State (pagination, sorting) is no longer saved in the local storage. When navigating to the case list page
    of a document definition, the default state as configured in the environment file or in the API is shown.
  * The current assignee filter is now saved in query parameters in the URL.
  * When navigating to a case list page using a URL with query parameters, the list state (pagination, sorting, search,
    assignee filter) is restored from these parameters. This includes going back to the case list page from a case
    detail page using the back button.


* **Task forms are now retrieve using a new API**

  When opening a user task, the form is now loaded using the new API endpoint:

  ```GET /api/v2/process-link/task/{id}```

* **Upgraded deprecated `carbon-components` package in `@valtimo/components` to `@carbon/styles`**

  One of the Carbon Design System packages was deprecated and has been upgraded to the new package

## Bugfixes

The following bugs were fixed:

* **Context detail not loading properly**

  Fixed an issue where the buttons next to the processes weren't initialized properly.

* **Modal dispersal on error when creating an object in Object management**

  The modal will now stay open and an error will be shown when used enters invalid information when creating an object.

* **Case list bug fixes**

  In conjunction with the case list refactor mentioned under new features, the following issues were fixed:
  * Boolean values (displayed as Yes/No) are now translated.
  * When navigating to a case list page without query parameters, the default sort as specified in an environment file
    or in the API is now used on first load.
  * Date formats specified in list columns of type date are used to correctly display the date value in the desired
    format.

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
