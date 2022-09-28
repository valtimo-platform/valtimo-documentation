# Backend libraries 9.19.0

## New Features

The following features were added:

* **Filter out plugin configurations without actions of a service type**

  The plugin configuration can now be filtered based on an activityType (i.e. Service Task), that will 
  ensure that any plugin configuration that is returned has an action for that activityType. 

  The REST endpoint `GET /api/plugin/configuration` now supports a new request parameter
  called `activityType` which expects the type of task that was clicked in the process. 
  Example: `GET /api/plugin/configuration?activityType=bpmn:ServiceTask`.

* **New form flow `onBack` property**

  Form flows already supported the `onOpen` and `onComplete` properties. The `onBack` property has been added that is
  triggered when navigating to a previous step. Information on how to use these properties in a form flow can be found
  [here](/using-valtimo/form-flow/create-form-flow-definition.md#expressions).

## Bugfixes

The following bugs were fixed:

* **JdbcProcessFormAssociationRepository insert statement runtime exception**

  Running on an externally hosted Mysql 8.0.15 instance caused unknown column type exceptions with `useServerPrepStmts`. For more information [see](https://github.com/brettwooldridge/HikariCP/wiki/MySQL-Configuration).
  To prevent determining the sql column type now the type is specified.

## Breaking changes

The following breaking changes were introduced:

* **Form flow `onBack` property is null for existing records**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

No new deprecations.

## Known issues

This version has the following known issues:

* **Multiple existing form associations on process definition**

  When multiple start forms are associated with a single process definition the user is unable to start a new case of
  that specific type.
