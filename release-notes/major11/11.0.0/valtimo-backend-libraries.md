# Backend libraries 11.0.0

## New Features

The following features were added:

* **Policy Based Access Control (PBAC)**

  Valtimo now supports Policy Based Access Control (PBAC), which provides detailed authorization checks on actions and data.
  More information can be found here:
  * [Introduction](/introduction/modules/modules.md#authorization)
  * [Getting started](/getting-started/modules/core/authorization.md)
  * [Using Valtimo](/using-valtimo/access-control/access-control.md)
  

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.


## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Removed REST endpoints**
  Several endpoints were meant for public use. By default, Valtimo should not offer any public endpoints,
  and as a result these have been removed. This is the list of removed endpoints:
  * `/api/v1/public/process/definition/{processDefinitionKey}/start-form`
  * `/api/v1/public/process/definition/{processDefinitionKey}/{businessKey}/start`
  * `/api/v1/public/task/{taskDefinitionId}/resource/pre-signed-url/{fileName}`
  * `/api/v1/public/task/{taskDefinitionId}/resource/{resourceId}`
  * `GET /api/v1/document-definition/{name}/roles`
  * `PUT /api/v1/document-definition/{name}/roles`
  * `GET /api/v1/document-definition?filteredOnRole=false`
    * Has been replaced by `GET /api/management/v1/document-definition`

* **Removed classes**
  Several classes have been removed in favor of PBAC policies:
  * JsonSchemaDocumentDefintionRole
  * JsonSchemaDocumentDefintionRoleId

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
