# Migration

This page describes how to update Valtimo from the previous version to the current.

* **FormFieldDataResolver `get` method is deprecated**

  1. **Implement the new `get` method**

      Add method `get(String documentDefinitionName, UUID documentId, JsonNode formDefinition, String... varNames)` to your class and move the logic from the deprecated `get` to this new method

  2. **Invoke new `get` from deprecated `get`**  

      ```
      override fun get(documentDefinitionName: String, documentId: UUID, vararg varNames: String): Map<String, Any> {
          return get(
              documentDefinitionName = documentDefinitionName,
              documentId = documentId,
              formDefinition = Mapper.INSTANCE.get().createObjectNode(),
              varNames = varNames
          )
      }
      ```
