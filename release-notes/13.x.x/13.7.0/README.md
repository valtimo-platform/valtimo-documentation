# 13.7.0

{% hint style="info" %}
**Release date Day-Month - Year**
{% endhint %}

## New Features

* **Retry cycles for failed jobs**

Standard Retry cycles are defined which can be added to the following BPMN elements:
* Tasks
* Call Activities
* Sub processes
* Events

The following retry cycles are available:
* DEFAULT = R3/PT1M,PT30M,PT2H
* QUICK = R3/PT30S,PT2M,PT10M
* CRITICAL = R5/PT1M,PT15M,PT4H,PT24H,PT48H

These retry cycles can be customized in application.yml.
In addition, custom cycles can be defined through Spring Boot configuration files.

see more about it [here](../../features/process/retry-cycle.md)

## Enhancement

* **Enhancement title**

  Enhancement description


## Bugfixes

* Resolved issue where there was no option to use current date/time in the set-zaakstatus action of the zaken-api-plugin.
