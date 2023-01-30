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

* **Process beans**

  For documentation on Spring beans, see the Spring documentation [here](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html).
  

  By default, all beans are available for use within a BPMN, e.g. to send and email. By setting the
  `valtimo.camunda.bean-whitelisting = true` property in the `application.yml`, only whitelisted beans are available.
  Beans can be whitelisted by defining them with the `@ProcessBean` annotation.


## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

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
