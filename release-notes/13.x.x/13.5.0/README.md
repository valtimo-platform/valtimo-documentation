# 13.5.0

{% hint style="info" %}
**Release date 05-November - 2025**
{% endhint %}

## New Features

* **Performance improvements**

Significant performance improvements when retrieving tasks and cases, smaller performance improvements everywhere else.

* **Improved logging for developers**

This release includes an internal improvement to how Valtimo logs request and response data.  
When working with JSON-based integrations, log entries are now automatically formatted to be easier to read.

* **Zaken-API plugin updates**

An action was added to the Zaken-API plugin, allowing to delete a Zaak-role.

## Enhancements

* **Updated dependencies**

  The following dependencies were updated:
  * Spring Boot (`3.4.5` &rarr; `3.5.7`)
  * Operaton (`1.0.0-beta-4` &rarr; `1.0.0-rc-1`)
  * Everit Json Schema (`1.14.5` &rarr; `1.14.6`)
  * Commons Validator (`1.9.0` &rarr; `1.10.0`)
  * Commons Lang 3 (`3.17.0` &rarr; `3.19.0`)
  * Guava (`33.4.8-jre` &rarr; `33.5.0-jre`)
  * Apache Tika (`3.1.0` &rarr; `3.2.3`)
  * GraalVM (`24.2.1` &rarr; `25.0.1`)

* **Improved Notificaties API processing**

The Notificaties API plugin now safely stores incoming notifications, prevents duplicates, processes them in the background with automatic retries and clean-up, and offers an admin view for failed messages together with a health check that warns when too many remain. 

Make sure to add the admin menu entry described [here](../../../features/plugins/configure-notificaties-api-plugin.md) so users can reach the new overview.

## Bugfixes

* Process links referencing forms are now always included when creating a new draft version of an existing case definition.
* Case tags and header widgets are now included when creating a new draft version of an existing case definition.
* When uploading a document, the field containing the document types is now always filled if any document types are available.
* When creating a new case widget, the conditions of the previously opened widget is no longer prefilled.
* The widget title of FormIO and custom widgets are now correctly displayed.
* The issue where after the case version update in Verzoeken plugin was no longer possible to create subscriptions and filters is resolved
* The layout of the widgets which contain more than 5 fields is improved
* The issue when the tabs get broken when the user is trying to switch between the tabs with the case open is resolved
* The OpenNotificaties abonnement is now registered after the application startup, rather than during initialization.
