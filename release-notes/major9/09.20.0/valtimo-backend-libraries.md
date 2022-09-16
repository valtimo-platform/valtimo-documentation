# Backend libraries 9.20.0 (RC)

## New Features

The following features were added:

* **Additional method for finding documents from within a process**

  The `search` method in the `JsonSchemaDocumentSearchService` does not work when retrieving a document if no
  authorization is found. A new method, `searchWithoutAuthorization` is now available. For classes that implement the 
  `DocumentSearchService`, this method has a default and only needs to be implemented if this use case is necessary.

* **Zaakobjecten can now be edited**

  When creating a form that includes a propertyName with "zaakobject:objecttype:path/to/variable" it will now be
  prefilled when loading the form. When submitting the form the corresponding zaakobject is updated with the new values
  
  The uploading is handled by a new `ExternalDataSubmittedEvent` handler called `ZaakObjectListener`

* **KeyCloak**

  KeyCloak libraries have been updated to 19.0.1. Older KeyCloak server versions are still supported.
