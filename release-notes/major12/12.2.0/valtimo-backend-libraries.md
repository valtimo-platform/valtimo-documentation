# Backend libraries 12.2.0

## New Features

The following features were added:

* **Update method for ObjectManagementFacade**

  Objects can now be updated using the `updateObject` method in the `ObjectManagementFacade`.

* **Implementations of `AuthorizationEntityMapper` now use repositories directly**

  Some AuthorizationEntityMappers used the service layer to retrieve related entities,
  which caused several events and checks to trigger as a side effect.
  This could potentially affect performance. They now use repositories directly.

* **Keycloak supports OAuth 2.0 authentication**

  Valtimo can connect to keycloak using OAuth 2.0 and OpenID Connect.
  See [this page](/using-valtimo/keycloak-iam/configuring-keycloak.md) for more information.

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
