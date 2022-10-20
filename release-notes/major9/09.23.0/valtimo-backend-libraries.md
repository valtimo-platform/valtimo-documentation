# Backend libraries 9.23.0 (RC)

## New Features

The following features were added:

* **Allow external fields to have a nested formfield.key structure**

  Previously an external field definition only supported 1 level keys like:
  - `ex.keyName`

  Now its possible to define nested stuctures like:
  - `ex.keyName.anotherKeyName`
    Resulting in structures that can be mapped into the prefilling/submission phase:
   ```json
   {
       "ex" : {
           "keyName" : {
                "anotherKeyName" : "someValue"
           }
       }
   }
  ```

* **A document can now be assigned to a user**

  There are two methods of assigning a user to a document.
  
  1) Using the endpoint `POST /api/document/{documentId}/assign` and providing the assignee id in the request body.
  ```json
  {
    "assigneeId" : "some UUID"
  } 
  ```
  2) Using an expression inside a process
  ```
  ${documentDelegate.setAssignee(execution, "assignee email address")}
  ```

* **A user can be unassigned from a document**

  When a user is assigned to a document he/she can be unassigned by calling
  `POST /api/document/{documentId}/unassign`

## Bugfixes

The following bugs were fixed:

* **Form flow incompatible with PostgreSQL**

  The Form flow module was failed when loading form flows from the configuration files when using the PostgreSQL DBMS. 
  This has now been resolved.

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
