# Frontend libraries 5.12.0 (RC)

## New Features

The following features were added:

* **Added default assignee column to the case list**

  Added a new default column to the `valtimo-dossier-list` component, which displays the full name of the assignee 
  for each case when it exists. This column is sortable, considering the first name and then the lastname.

  To display the new column, it was necessary to add data in the `environment.ts` file (see example below).
  #### **`environment.ts`**

  ```typescript
  export const environment: ValtimoConfig = { ...
    {
    propertyName: 'assigneeFullName',
    translationKey: 'assigneeFullName',
    sortable: true,
    }
   }
  ```

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
