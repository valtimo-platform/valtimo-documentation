# Backend libraries 12.2.0

## New Features

The following features were added:

* **Update method for ObjectManagementFacade**

  Objects can now be updated using the `updateObject` method in the `ObjectManagementFacade`.

* **Implementations of `AuthorizationEntityMapper` now use repositories directly**

  Some AuthorizationEntityMappers used the service layer to retrieve related entities,
  which caused several events and checks to trigger as a side effect.
  This could potentially affect performance. They now use repositories directly.

* **Dependency upgrades**

  The following libraries were upgraded to new versions:

  | Dependency                            | Old version     | New version     |
  |:--------------------------------------|:----------------|:----------------|
  | Kotlinx Coroutines                    | `1.8.0`         | `1.8.1`         |
  | Spring Boot Admin Starter Client      | `3.2.3`         | `3.3.3`         |
  | Spring Cloud starter Stream Rabbit    | `4.1.1`         | `4.1.3`         |
  | Liquibase                             | `4.24.0`        | `4.29.0`        |
  | Commons Lang                          | `3.14.0`        | `3.15.0`        |
  | Commons Codec                         | `1.17.0`        | `1.17.1`        |
  | Commons Validator                     | `1.8.0`         | `1.9.0`         |
  | JJWT                                  | `0.12.5`        | `0.12.6`        |
  | GraalVM JS                            | `23.0.4`        | `23.0.5`        |
  | Hypersistence Utils                   | `3.7.4`         | `3.8.2`         |
  | Keycloak Client                       | `24.0.3`        | `24.0.5`        |
  | Classgraph                            | `4.8.172`       | `4.8.174`       |
  | Guava                                 | `33.1.0-jre`    | `33.2.1-jre`    |
  | Spring Doc OpenAPI Starter WebMVC API | `2.3.0`         | `2.6.0`         |
  | AWS SDK                               | `2.23.8`        | `2.26.25`       |
  | Jackson                               | `2.17.0`        | `2.17.2`        |
  | JUnit                                 | `5.10.2`        | `5.10.3`        |
  | MySQL Connector-J                     | `8.3.0`         | `8.4.0`         |
  | Hibernate                             | `6.2.24.Final`  | `6.5.2.Final`   |
  | Shedlock                              | `5.13.0`        | `5.14.0`        |
  | Netty Codec                           | `4.1.106.Final` | `4.1.112.Final` |

* **Tasks list can now be added to any case tab**

  When configuring a case tab, it is now possible to show the task list on that tab. This list was previously only shown on the summary tab.
  For more information, please see [this page](/using-valtimo/case/case-tabs.md#example)

* **Valtimo uses Spring OAuth for authentication with Keycloak**

  Valtimo can connect to keycloak using OAuth 2.0 and OpenID Connect.
  See [this page](/using-valtimo/keycloak-iam/configuring-keycloak.md) for more information.


## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.