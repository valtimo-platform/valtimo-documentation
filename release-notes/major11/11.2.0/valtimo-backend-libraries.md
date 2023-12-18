# Backend libraries 11.2.0

## New Features

The following features were added:

* **Export case definitions**

  Case definitions can now be exported as an archive, containing all process definitions, forms, form flows,
  process links and the document definition that make up the case definition. See 
  [this page](/using-valtimo/case/exporting-case-definitions.md#export) for more information.

* **Import case definitions**

  Case definitions can now be imported from a ZIP archive, containing all process definitions, forms, form flows,
  process links and the document definition that make up the case definition. See
  [this page](/using-valtimo/case/exporting-case-definitions.md#import) for more information.

* **Transactional outbox**

  Valtimo now supports an implementation of
  the [transactional outbox pattern](https://microservices.io/patterns/data/transactional-outbox.html). See
  [this page](/getting-started/modules/core/outbox.md) for more information.

* **Audit CloudEvents**

  Several outbox events have been added for auditing purposes. For an overview of the available events, refer to
  [this page](/reference/modules/outbox.md)

* **Outbox message publisher for RabbitMQ**

  A RabbitMQ (AMQP 0.9.1) message publisher has been in the `outbox-rabbitmq` module. More information can be found [here](/getting-started/modules/core/outbox-rabbitmq.md). 

* **Added option for custom process variable name to download document plugin action in documentAPI**

  Added option for custom process variable name to download document plugin action in documentAPI so you have the option to choose a custom process variable name.
  When left empty the default name is: "resourceId"

* **Selecting and retrieving a specific version of a document definition**
  
  To support switching between document definition versions, two new API endpoints have been added. The first is to
  retrieve a list of versions available for that document definition, and the second to retrieve a specific version:
  - ```GET /api/management/v1/document-definition/{name}/version```
  - ```GET /api/management/v1/document-definition/{name}/version/{version}```

## Bugfixes

The following bugs were fixed:

* **Deadlock**

  Solved a deadlock that could happen under certain conditions when modifying the document inside a BPMN process.

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