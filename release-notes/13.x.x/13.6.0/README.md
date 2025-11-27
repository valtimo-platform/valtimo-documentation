# 13.6.0

{% hint style="info" %}
**Release date xx-November - 2025**
{% endhint %}

## New Features

**Date status set added to zaken api plugin**

  A new field has been added to the set-zaakstatus action in the Zaken API plugin that allows setting the date of a zaak-status.

* **Map widget**

  A new case widget type has been added called the _map widget_. This widget shows a world map with geometry drawn on top of it.

## Bugfixes

* When the `disableCaseCount` feature toggle is set to `true`, the number of open cases will no longer be shown in the menu.
* Migrations to Valtimo 13 now take into account usernames that look like email addresses to find the correct users in Keycloak.
* General performance improvements for migration scripts when retrieving users from keycloak.
