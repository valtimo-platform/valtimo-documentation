# Backend libraries

## New Features

The following features were added:

* **Camunda webapps**

  The Camunda webapps, including the cockpit, were made available. For existing Valtimo projects additional
  infrastructure configuration might be required to grant access to the `/camunda/app` path. See
  [this page](/valtimo-implementation/modules/camunda-webapps.md) for more information.

* **Plugins**

  Plugins are extensions on the Valtimo platform. These are often connections to external
  services, such as transactional email and generating documents. Some plugins are provided
  by the platform, but developers can create their own plugins as well. Plugins can be
  configured without writing code, and can be used during BPMN processes. See
  [this page](/introduction/modules/plugin-introduction.md) for more information.

* **Smart documents plugin**

  A Smart documents plugin has been created. This is the very first valtimo plugin.

## Bugfixes

The following bugs were fixed:

* **Input sanitization for pre-filled fields inside of forms**

  When a form definition is pre-filled, the pre-filled fields were prone to HTML injection. These fields are now
  sanitized when the fields are pre-filled.

* **Slow form association retrieval**

  Form associations are retrieved on several locations within the application. For example, when opening a task a form
  is retrieved. Retrieving this form became very slow when many forms had been associated to a single process. To solve
  this issue, form associations are no longer stored as JSON in the database. JSON fields can't be indexed which made
  the form associations slow. Form associations are now stored in a new table with proper indexing and without JSON
  columns.

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
