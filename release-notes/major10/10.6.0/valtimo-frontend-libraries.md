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
