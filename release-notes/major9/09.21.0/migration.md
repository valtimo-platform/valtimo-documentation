# Migration

This page describes how to update Valtimo from the previous version to the current.

* **FormFieldDataResolver `get` method is deprecated**

  1. **Implement the new `get` method**

      Add method `get(String documentDefinitionName, UUID documentId, FormFieldDataResolverProperties additionalProperties, String... varNames)` to your class and move the logic from the deprecated `get` to this new method
