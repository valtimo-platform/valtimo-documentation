# Frontend libraries 5.12.0 (RC)

## New Features

The following features were added:

* **Added default assignee column to the case list**

  Added a new default column to the `valtimo-dossier-list` component, which displays the full name of the assignee
  for each case when present. This column is sortable, considering the first name and then the lastname.

  To display the new column, it is required to add data in the `environment.ts` file (see example below).
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

* **Added modifier property to customDossierHeaderItems**
  
  In a `customDossierHeaderItem` you can now pass a `modifier` property to modify how the data for the
  header item is rendered. The only allowed modifier at this moment is the `age` modifier which renders
  a date string as an age (see example below).

  ```typescript
  customDossierHeader: {
    dossierName: [
      {
        labelTranslationKey: 'Age',
        propertyPaths: ['personA.dateOfBirth'],
        modifier: 'age'
      }
    ]
  }
  ```
  

## Bugfixes

The following bugs were fixed:

* **Semicolon in customDossierHeaderItem**

  The semicolon between label and value in custom dossier header items were rendered when only a `labelTranslationKey`
  was defined. It will now only render a semicolon when both the `labelTranslationKey` and the `propertyPaths` are
  defined.

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
