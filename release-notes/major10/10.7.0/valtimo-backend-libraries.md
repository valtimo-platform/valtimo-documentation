# Backend libraries 10.7.0

## New Features

The following features were added:

* **Security smoke testing**

  A new test class is made available to quickly check if all REST API endpoints apply some form of security using the
  new `SecuritySmokeIntegrationTest`. More information [here](/extending-valtimo/test-utils-common/security-testing.md).

* **Automatic User Task assignment to Case Handler**

  It is now possible to have user tasks automatically assigned to a case handler.
  Refer [to this page](/using-valtimo/document/automatic-task-assignment.md) to learn more about this feature.

* **Additional status on TaakObject**

  An additional status option `GESLOTEN` has been added to the 
  [TaakStatus](https://github.com/valtimo-platform/valtimo-backend-libraries/blob/main/zgw/portaaltaak/src/main/kotlin/com/ritense/portaaltaak/TaakObject.kt#L49)
  enum of a TaakObject.

* **Whitelisting by mime-type of files uploaded to temporary file storage**
  The types of files uploaded to the temporary file storage can now be restricted by whitelisting allowed mime-types.
  More information on this feature can be found [here](/using-valtimo/upload/temporary-file-storage.md#whitelisting-file-types-for-uploads)

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.

## Bugfixes

The following bugs were fixed:

* **Limit ClassGraph scanning**

  In rare cases an out of memory error could occur due to ClassGraph scanning all packages. This has been resolved by
  introducing a blacklist of libraries that don't need to be scanned.

* **Summary pages fail to load because of duplicate process variables**

  When one or more processes had multiple process variables of the same name, the summary page for the related case would
  no longer load. Since process variables should not be used for the summary, these are no longer retrieved.

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

* **Main application in alternative package does not work properly**
  * Discovered in version 10.7.0
  * When the main Spring Boot application class (annotated with `@SpringBootApplication`) is not
    in `com.ritense.valtimo`, some configurations are not picked up properly. Known features that will be impacted are:
    * **Audit log**: view does not show any logs.
    * **Exception handling**: Exceptions are not translated to the correct http status codes. For instance,
      a `AccessDeniedException` results in a status `500` instead of `403`.
  * As a workaround, the following can be added to your main application
    class: `@SpringBootApplication(scanBasePackages = {"com.ritense.valtimo", "your.custom.package"})`.

* **Issue2**
    * Discovered in version x.x.x
    * Describe what can be done to work around the issue
