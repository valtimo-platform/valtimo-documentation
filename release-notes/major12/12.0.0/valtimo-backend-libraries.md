# Backend libraries x.x.x

## New Features

The following features were added:

* **valtimo-dependency-versions module**

  A new `valtimo-dependency-versions` module has been created, 
  which at the same time removes the version control from `valtimo-dependencies` and `valtimo-gzac-depenencies`.

  This module specifies versions for dependencies of Valtimo.

  More information can be found [here](../../../getting-started/modules/core/valtimo-dependency-versions.md).

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

* **Upgrade to Spring Boot 3**

  Valtimo has been upgraded to Spring Boot 3.
  This was needed to keep the product up to date with the latest (transitive) dependencies.

  Migration instructions related to this change can be found [here](spring-boot3-migration).

* **Valtimo dependencies have changed**
  `valtimo-dependencies` and `valtimo-gzac-depenencies` should no longer be used for `dependencyManagement` or `platform`. 
  This functionality has been replaced by [valtimo-dependency-versions](../../../getting-started/modules/core/valtimo-dependency-versions.md).

* **Removed deprecated code**
  The `form-link` module, which was deprecated in 10.6.0, has been removed. Process links should be used instead.
  Additionally, `CamundaProcessJsonSchemaDocumentService.getDocument(DelegateExecution execution)` has been removed.
  This method is replaced by `DocumentDelegateService.getDocument(DelegateExecution execution`.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **Audit module methods**

  Several methods have been deprecated as they were not used for anything. No alternatives are offered.
  These are:
  * `AuditRecordRepository.findAuditRecordByProperty(String key, Object value, Pageable pageable)`
  * `AuditService.findByEventAndOccurredBetween(Class<? extends AuditEvent> event, LocalDateTime from, LocalDateTime until, Pageable pageable)`
  * `AuditService.findByProperty(String key, Object value, Pageable pageable)`
  * `AuditService.findByEventTypeAndProperty(Class<? extends AuditEvent> event, String key, Object value)`
  * `AuditSearchService`

* **Audit module classes**

  The `AuditSearchService` class has been deprecated as it was not used for anything.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Issue1**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue

* **Issue2**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue
