# Frontend libraries 5.7.0 (RC)

## New Features

The following features were added:

* **Digit only input**

  The `v-input` component exported from `@valtimo/user-interface` now supports a new type input: `'digitOnly'`. This
  option displays a text input field which only accepts numbers as input.

* **Improved tooltips**

  Various tooltips for plugin configuration components have been added or improved.

* **Improved the select component of the @valtimo/user-interface library**
  * **Background color change**

    The select component has been improved to follow the default input style and make it visibly indicated when a 
  dropdown menu is enabled/disabled.
    
    The look of the default component's background style color has been changed to white (`--v-color-white`) to 
    distinguish it from the disabled state.
  
  * **Contrast and color updates**

    * Add shadow to the `v-select` element to add contrast.

    * Changed text color to `--v-color-grey-0` when option selected in dropdown.

  * **Changed and created new color variables for the `v-select` element**
    
    * Changed:
    
    `--v-select-background-color: var(--v-color-white);`

    * New:
    
    `--v-select-darker-font-color: var(--v-color-grey-0);`
    
    `--v-select-disabled-bg-color: var(--v-color-grey-4);`


## Bugfixes

The following bugs were fixed:

* **Refactor of case list component**

  In developing new features for the case list component, it was discovered that the component contained quite a few bugs
  which were hard to fix. It was decided to refactor the component using observables. The following should now work
  without bugs:
  * On case definition load: get pagination (including sorting) from local storage. If this does not exist, get default
    pagination and sorting from the environment file.
  * Go to the first page when typing in a search term or sequence number.
  * Switch to last available page on choosing a larger page size.
  * On switching case definitions, the page indicator shows the correct page number.
  * When switching case definitions, the correct cached sort state or default sort state is retrieved.

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
