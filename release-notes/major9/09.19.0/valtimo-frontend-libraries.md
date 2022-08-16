# Frontend libraries 5.7.0 (RC)

## New Features

The following features were added:

* **Improved the select component of the @valtimo/user-interface library**
  * **Background color change**

    To follow the default input style on the form and make it visibly indicated when a dropdown menu is activated, 
  the component's background style color has been changed to `--v-color-white`.
    In this way, reaching the objective of clarity and bringing a more pleasant and standardized layout.

  * **Contrast and color updates**
    
    * Add shadow to the `v-select` element in order to add contrast. 
    
    * Changed text color to `--v-color-grey-0` when option selected in dropdown.

  * **Changed and created new color variables for the `v-select` element**
    
    * Changed:
    
    `--v-select-background-color: var(--v-color-white);`

    * New:
    
    `--v-select-darker-font-color: var(--v-color-grey-0);`
    
    `--v-select-disabled-bg-color: var(--v-color-grey-4);`


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
