# Migration

This page describes how to update Valtimo from the previous version to the current.

* **FormFieldDataResolver `get` method is deprecated**

  1. **Implement the new `get` method**
     
      Add method `get(DataResolvingContext dataResolvingContext, String... varNames)` to your class and move the logic from the deprecated `get` to this new method. 
      The parameters `String documentDefinitionName` and `UUID documentId` are moved to the `DataResolvingContext` object. 
