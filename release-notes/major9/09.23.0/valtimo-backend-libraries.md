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

  It is now possible to assign (and unassign) a user to a document. 

  For more information on using this feature see [this page](/using-valtimo/document/assigning-a-user.md).
 
  Information about the endpoints can be found [here](/extending-valtimo/document/assigning-and-unassigning-a-user.md).


## Bugfixes

The following bugs were fixed:

* **Form flow incompatible with PostgreSQL**

  The Form flow module was failed when loading form flows from the configuration files when using the PostgreSQL DBMS. 
  This has now been resolved.
