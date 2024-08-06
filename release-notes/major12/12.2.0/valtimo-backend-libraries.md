# Backend libraries 12.2.0

## New Features

The following features were added:

* **Update method for ObjectManagementFacade**

  Objects can now be updated using the `updateObject` method in the `ObjectManagementFacade`.

* **Introduced a new database table**
  
  The table `resource_storage_metadata` creates a link between the (form io) file id and the (documenten api) 
  document id and download url

* **The system proces `Documenten API upload document` has a new system task**
  
  The new system task will publish a `ResourceStorageMetadataAvailableEvent`. The parameters in this event are used to
  store in the new `resource_storage_metadata` database table

* **New api for Temporary Resource Storage**

  The `GET /v1/resource-storage/{resourceStorageFieldId}/metadata/{metadataKey}` will return a metadata value
  for the provided (form io) field id) and the metadata key. 
  There currently are two allowed metadataKeys: `downloadUrl` and `documentId`

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
