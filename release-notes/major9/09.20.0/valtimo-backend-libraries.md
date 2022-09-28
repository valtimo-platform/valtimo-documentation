# Backend libraries 9.20.0

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

## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No new deprecations.

## Known issues

This version has the following known issues:

* **Multiple existing form associations on process definition**

  When multiple start forms are associated with a single process definition the user is unable to start a new case of
  that specific type.

* **Using formAssociationService.createFormAssociation() on application startup causing the application to crash**

  When form associations are created on application startup using the formAssociationService.createFormAssociation() method, these associations are duplicated. Before   the bugfix in this release these duplicated associations were added without errors. After the bugfix in this release the application will throw an exception when       creating an already existing association, causing the application to crash on startup.

  Solution: the correct way to add form associations is by adding [form link files](/using-valtimo/form-link/configure-task.md). Using of          formAssociationService.createFormAssociation() should be replaced with form link files.
