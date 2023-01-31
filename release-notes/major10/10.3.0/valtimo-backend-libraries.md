# Backend libraries 10.3.0

## New Features

The following features were added:

* **Added Portaaltaak plugin**

  This plugin makes it possible for Valtimo to communicate and interact
  with a Portal task specification compliant ZGW component.

* **Valtimo dependencies**

  Two new modules have been introduced to help with managing dependencies. These are [Valtimo dependencies](/getting-started/modules/core/valtimo-dependencies.md) and
  [Valtimo GZAC dependencies](/getting-started/modules/zgw/valtimo-gzac-dependencies.md). Including these dependencies
  in a project will automatically include the core modules for that edition of Valtimo, which also improves the
  experience when upgrading Valtimo to a new version.

* **Plugin Events**  
It is now possible to have plugin methods run whenever a plugin configuration created, updated or deleted. 
More information on this feature can be found [here](/extending-valtimo/plugin/custom-plugin-definition.md#plugin-events).

* **Improved Notificaties API plugin**  
The following improvements have been made to this plugin:
  * An additional input is required when configuring the plugin: `callbackUrl`. This is required by Notificaties API to know where to send notification requests.
  * Plugin Events have been implemented so that a Notificaties API subscription is made, updated or removed when the corresponding interaction is done with the Plugin.


## Bugfixes

The following bugs were fixed:

* **Fixed Notificaties API response mapping**

  The response from OpenNotificaties when creating a subscription is missing a required property. This was causing a Runtime Exception while mapping the response.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Changed Notificaties API Abonnement Link database table column**  
A Liquibase changeset was added to modify the column name.

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
