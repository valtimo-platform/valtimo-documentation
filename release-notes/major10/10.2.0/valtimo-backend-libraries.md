# Backend libraries 10.2.0

## New Features

The following features were added:

* **Added new Notificaties API plugin**

  This plugin makes it possible for valtimo to communicate and interact 
  with a Notificaties API specification compliant ZGW component.

* **Added new OpenNotificaties plugin**

  This plugin facilitates authentication for the Notificaties API plugin when interfacing 
  with [OpenNotificaties](https://github.com/open-zaak/open-notificaties).

* **Automatically migrate linked plugin actions**

  Plugin actions that are linked to the latest process version will now automatically be linked to a new version of
  the process that is being deployed.

## Bugfixes

The following bugs were fixed:

* **Multiple form flow instances linked to task**

  In some situations when a user tried to open a user task multiple times, the user would get the error: 'Multiple form
  flow instances linked to task'. This has been fixed for every new user tasks that is created after the upgrade to
  10.2.0. Users can still get the error when opening an old user task.

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