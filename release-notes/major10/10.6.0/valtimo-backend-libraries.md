# Backend libraries 10.6.0

## New Features

The following features were added:

* **New plugin action to set the zaak status**

  The Zaken Api plugin has a new plugin action to set the zaak status.

* **New plugin action to create a 'Zaakresultaat'**

  The Zaken Api plugin has a new plugin action to create a 'Zaakresultaat'.

* **New plugin action to create a 'Zaakbesluit'**

  The Besluiten Api plugin has a new plugin action to create a 'Zaakbesluit'.

* **New plugin action to link a Document to a Besluit**

  The Besluiten Api plugin has a new plugin action to link a Document to a Besluit.

* **Job service**

  A process bean to manipulate camunda jobs. For now, only manipulation of timer event dates is supported. This is
  useful when a timer has to be changed after it has already started. For more information,
  see [here](/using-valtimo/process/process-beans/job-service.md).

* **API responses now include charsets**

  All Valtimo API responses now include a character set in the Content-Type header. The Character set has been set to
  UTF-8.

* **New API endpoint to retrieve prefilled forms**

  A new API endpoint has been added to retrieve prefilled forms that are configured in the Process-Links menu:

  ```GET /v2/process-link/task/{taskId}```

* **Extended process link API endpoints**

  All API endpoints below have been extended. They used to only work with plugins. Now hey now also work with Forms
  and Form-flows.

  ```GET /api/v1/process-link```

  ```POST /api/v1/process-link```

  ```PUT /api/v1/process-link```

  ```DELETE /api/v1/process-link/{processLinkId}```

* **Updated dependency versions**

  Many dependencies have been updated. A few of the dependency updates:
    - `org.camunda.bpm:camunda-engine` has been updated to version 7.19.0
    - `org.yaml:snakeyaml` has been updated to version 2.0
    - `org.keycloak:keycloak-admin-client` has been updated to version 21.1.0

  Versions of other dependencies can be
  found [here](https://github.com/valtimo-platform/valtimo-backend-libraries/blob/10.6.0.RELEASE/gradle.properties).

* **Deprecate OpenZaak Connector**

  The OpenZaak Connector has been deprecated. It can be replaced by
  the [Zaken API plugin](/using-valtimo/plugin/zaken-api/configure-zaken-api-plugin.md). The OpenZaak Connector will be
  removed entirely in Valtimo v12.

* **Process links configuration autodeployment**

  Process links can now be created by adding a configuration file in Valtimo. This configuration file is automatically
  used when rebooting Valtimo. More
  information [here](/using-valtimo/process-link/create-process-link.md#configuration-by-autodeployment)

* **New REST API endpoints have been added**

  A new endpoint has been added to return a prefilled Form IO form that was configured on a start-event of a BPMN:

  `GET /api/v1/process-definition/{process-definition-id}/start-form`

  A new endpoint has been added to return a list of process-link-types with a single property 'enabled'. The property '
  enabled' is true when the process-link-type is enabled for the specified activity-type:

  `GET /api/v1/process-link/types?activityType={activityType}`

## Bugfixes

The following bugs were fixed:

* **Reuse user var instead of retrieving it again**

  In the document service when creating a case `var user` was not re-used instead `SecurityUtils.getCurrentUserLogin())`
  was used again leading to having a possible different username when creating a case or attaching documents.

* **Reorder object columns**

  Fixed changing the ordering of list-columns and search-fields.

* **Not all uses shown in candidate users dropdown**

  The dropdown list with candidate users on a case page, now shows all users. There was a bug that cases the API
  endpoint to not respond with all users when there were more than 200 Keycloak users.

* **Maximum of 20 SmartDocument placeholders**

  The maximum number of 20 SmartDocument placeholders has been removed. It is now possible to enter many more
  placeholders. The maximum has been removed for all multi-input components within Valtimo. Which means that the maximum
  has also been removed for other features, such as the Verzoeken plugin mapping.

* **Object management list column date format**

  The list columns of Object API objects now displays dates with the configured date format.

* **Objecten API search bugfixes**
  
  Several bugs have been fixed for the Objecten API search:
  - The search now properly searches through nested properties using a different path notation.
  - It is now possible to search for properties with data type 'boolean'.
  - It is now possible to search for properties with data type 'date'.
  - It is now possible to search for properties with data type 'datetime'.

## Breaking changes

The following breaking changes were introduced:

* **Object search path**

  The path -field that is used for searching for objects, has changed. It now uses the following notation:

  ```obj:/customer/name```

  There is no need to manually change the path. Applications that upgrade to 10.6.0 are automatically migrated.

* **Renamed some classes in favor of Process links:**
    * ProcessLinkTaskProvider.java → FormLinkTaskProvider.java
    * FormProcessLinkTaskProvider.java → FormFormLinkTaskProvider.java
    * PluginProcessLinkResource → ProcessLinkResource
    * CopyPluginActionsOnProcessDeploymentListener → CopyPluginLinkOnProcessDeploymentListener

* **Other changes in favor of Process links:**
    * `ProcessLinkResource` bean name has changed to `formProcessLinkResource`
    * `ProcessLinkService` bean name has changed to `formProcessLinkService`
    * `PluginProcessLink.id` is now of type `UUID`
    * `PluginProcessLink.activityType` is now of type `ActivityTypeWithEventName`
    * `PluginProcessLinkCreateDto.activityType` is now of type `ActivityTypeWithEventName`
    * `PluginProcessLinkResultDto` has a new mandatory constructor property `activityType`
    * `PluginProcessLinkResultDto.activityType` is now of type `ActivityTypeWithEventName`
    * `PluginProcessLinkRepository` no longer extends `JpaRepository`

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
