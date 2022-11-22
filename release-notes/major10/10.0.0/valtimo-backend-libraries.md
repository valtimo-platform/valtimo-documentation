# Backend libraries 10.0.0

## New Features

The following features were added:

* **Dependency upgrades**

  The following libraries were upgraded to new versions:

| Dependency              | New version | Old version |
|:------------------------|:------------|:------------|
| Camunda                 | 7.18        | 7.14        |
| Camunda Mockito         | 6.17.1      | 6.17.0      |
| Camunda Platform Assert | 15.0.0      | 1.2         |
| Liquibase               | 4.16.1      | 4.3.3       |
| Spring Boot             | 2.7.5       | 2.5.12      |
| Spring Retry            | 1.3.4       | 1.2.5       |
| Kotlin                  | 1.7.20      | 1.6.10      |
| Kotlin coroutines       | 1.6.4       | 1.6.0       |
| Kotlin logging          | 3.0.2       | 2.0.4       |
| Mockito Kotlin          | 4.0.0       | 2.2.0       |
| Hibernate types         | 2.20.0      | 2.12.1      |
| MockWebServer           | 4.10.0      | 4.9.3       |
| Jackson                 | 2.13.4      | 2.13.3      |
| JUnit                   | 5.9.1       | 5.7.2       |
| Java JWT                | 0.11.5      | 0.11.2      |
| Apache commons Lang     | 3.12.0      | 3.8.1       |
| Apache commons IO       | 2.11.0      | 2.8.0       |
| Apache commons Text     | 1.10.0      | 1.9         |
| Apache Tika             | 2.5.0       | 1.18        |
| Problem Spring Web      | 0.27.0      | 0.25.2      |
| MyBatis                 | 3.5.11      | 3.5.0       |
| JSON Schema Validator   | 1.14.1      | 1.12.1      |
| zjsonpatch              | 0.4.12      | 0.4.11      |
| Bucket4j                | 8.1.1       | 4.10.0      |
| Mapstruct               | 1.5.3       | 1.3.0       |
| Keycloak Client         | 19.0.3      | 19.0.1      |
| ClassGraph              | 4.8.149     | 4.8.147     |
| Guava                   | 31.1-jre    | 28.2-jre    |


* **Support for MySQL 8**

  Official support for MySQL 8 has been added. If your database server is running on MySQL 5.7, it is recommended to
  upgrade to MySQL 8. See [here](https://dev.mysql.com/doc/refman/8.0/en/upgrading.html) for instructions on how to
  upgrade a MySQL installation.

## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Java 17**

  Valtimo is now compiled on Java 17 and needs to run in a Java 17 environment.

* **View configurator module**

  The view configurator module that was used by the old AngularJS front-end has been removed.

* **Process data object relation**

  Process data object relations were a way to link a stored object to a running process. When document definitions were
  introduced, this functionality was made obsolete. Process data object relations have now been removed.

* **REST API versioning**

  Every REST endpoint exposed by Valtimo now contains a version, e.g. `/api/document` becomes `/api/v1/document`.
  This makes it easier to support multiple versions in the future in case of breaking changes in the REST API, without
  waiting for a new major version of Valtimo.

* **Removed JWT configuration properties**

  The properties `valtimo.jwt.base64encoding` and  `valtimo.jwt.tokenValidityInSecondsForRememberMe` have been removed as they were used in a closed-source module that is no longer supported.

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
