# Backend libraries x.x.x

## New Features

The following features were added:

* **valtimo-dependency-versions module**

  A new `valtimo-dependency-versions` module has been created, 
  which at the same time removes the version control from `valtimo-dependencies` and `valtimo-gzac-depenencies`.

  This module specifies versions for dependencies of Valtimo.

  More information can be found [here](../../../getting-started/modules/core/valtimo-dependency-versions.md).

* **User task assignees saved by user ID**

  The assignees of a user task are now saved in the database by their user ID. When implementations use keycloak, the
  assignee column from the task table in the databases is automatically migrated from email to user ID.

* **New endpoint to retrieve Zaaktypen**
  A new endpoint has been added to the zaken-api module to retrieve zaaktypen: `/api/management/v1/zgw/zaaktype`. 
  This replaces the `/api/v1/openzaak/zaaktype` endpoint from the openzaak module, which is now deprecated.
  The new endpoint requires at least one Zaken API Plugin to be configured.

* **Moved OpenZaak plugin to new `openzaak-plugin-authentication` module**
  Since the `openzaak` modules has been deprecated, the `OpenZaakPlugin` has been moved to the new `openzaak-plugin-authentication` module.
  The packages are still the same to keep it backwards-compatible without configuration migrations.

## Bugfixes

The following bugs were fixed:

* **Error in some plugin action properties**

  The plugin action property would throw an error when the plugin action property was set to a process variable that
  contained a list.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Upgrade to Spring Boot 3**

  Valtimo has been upgraded to Spring Boot 3.
  This was needed to keep the product up to date with the latest (transitive) dependencies.

  Migration instructions related to this change can be found [here](spring-boot3-migration).

* **Valtimo dependencies have changed**
  `valtimo-dependencies` and `valtimo-gzac-depenencies` should no longer be used for `dependencyManagement` or `platform`. 
  This functionality has been replaced by [valtimo-dependency-versions](../../../getting-started/modules/core/valtimo-dependency-versions.md).

* **Moved KvKProvider and BsnProvider.**
  The `KvKProvider` and `BsnProvider` and implementations (`ZaakKvKProvider` and `ZaakBsnProvider`)have been moved to the `zaken-api` module. 
  The [objects-api module](../../../getting-started/modules/zgw/objects-api.md) has been changed to use the relocated interfaces.
  Please be aware that the new implementations require at least one Zaken API Plugin to be configured.

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
