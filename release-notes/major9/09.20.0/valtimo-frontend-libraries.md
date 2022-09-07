# Frontend libraries 5.9.0 (RC)

## New Features

The following features were added:

* **Option to configure extra tabs for object type**

  Added option to configure and display tabs by zaak object type, so user can see all relevant data in to separate tab.
  
  This configuration is done in `environmente.ts` by adding one or more **definition name** that contains a list of 
  the name of object types, as shown in the following example.

#### **`environment.ts`**

  ```typescript
  export const environment: ValtimoConfig = { ...
    caseObjectTypes: {
      leningen: ['Boom', 'Straatverlichting']
    },
   }
  ```

  For more information on how to configure extra tabs for object type, see [this page](../../../extending-valtimo/tabs/configure-tab-object-type.md).


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
