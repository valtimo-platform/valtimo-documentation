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

    The select component has been improved to follow the default input style and to visually indicate when a dropdown menu is enabled or disabled.

    The default `v-select` component's background style color appearance has been changed to white to add contrast and distinguish it from the disabled state.

* **Added auto scrolling to modal**

  The `valtimo-modal` component now scrolls to the top when transitioning between form flow steps, and when switching pages in a Form.IO wizard.

* **Dossier detail tab with zaakobjecten**

  Added a tab page with a dropdown to select an object type which is linked to the current case. After selecting this
  type, a list of objects is shown of this type. To include this tab, add it to the `tabsFactory` in your implementation:

  #### **`app.module.ts`**
  ```typescript
  import {
  DefaultTabs,
  ...
  DossierDetailTabZaakobjectenComponent,
  ...
  } from '@valtimo/dossier';
  
  ...
  
  export function tabsFactory() {
    return new Map<string, object>([
      ...
      [DefaultTabs.zaakobjecten, DossierDetailTabZaakobjectenComponent],
      ...
    ]);
  }
  ```

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

* **Styling fix for the searchable dropdown component**
  
  The component `valtimo-searchable-dropdown`, exported by `@valtimo/components`, had styling issues locally. Its styling
  was conflicting with styling imported by [ng-multiselect-dropdown](https://www.npmjs.com/package/ng-multiselect-dropdown).
  Its class names have been made more specific in order to avoid these styling conflicts.

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
