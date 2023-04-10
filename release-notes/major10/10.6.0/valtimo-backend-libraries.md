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

* **New plugin actions in Catalogi API plugin**

  The following Catalogi API plugin actions have been added:
  - Retrieve Statustype
  - Retrieve Resultaattype
  - Retrieve Besluittype

* **Job service**

  A process bean to manipulate camunda jobs. For now, only manipulation of timer event dates is supported. This is useful when a timer has to be changed after it has already started. For more information, see [here](/using-valtimo/process/process-beans/job-service.md).

## Bugfixes

The following bugs were fixed:

* **Reuse user var instead of retrieving it again**

  In the document service when creating a case `var user` was not re-used instead `SecurityUtils.getCurrentUserLogin())` was used again leading to having a possible different username when creating a case or attaching documents.

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
