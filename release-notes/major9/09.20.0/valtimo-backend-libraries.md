# Backend libraries 9.20.0

## New Features

The following features were added:

* **Additional method for finding documents from within a process**

  The `search` method in the `JsonSchemaDocumentSearchService` does not work when retrieving a document if no
  authorization is found. A new method, `searchWithoutAuthorization` is now available. For classes that implement the 
  `DocumentSearchService`, this method has a default and only needs to be implemented if this use case is necessary.

## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No new deprecations.

## Known issues

This version has the following known issues:

* **Multiple form associations on process definition**

  When multiple start forms are associated with a single process definition the user is unable to start a new case of
  that specific type.
