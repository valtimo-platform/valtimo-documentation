# Backend libraries 10.1.0

## New Features

The following features were added:

* **Form flow bean for completing an associated task**

  A bean for Form Flow was added to make it easier to complete a Camunda user task from within a Form Flow. More
  information can be found [here](/reference/modules/form-flow.md#form-flow-spel-beans)

* **Form flow instance creation on task open**

  The Form flow instance is now created when a user task is opened. Users configuring the form flow can now make
  changes to the form flow that is connected to the user task, as long as the task isn't opened.

* **Form flow context contains extra variable**

  A variable called `instance.id` has been added to the SpEL context of a form flow expression. This variable contains
  the id of a form flow instance. More
  information can be found [here](/reference/modules/form-flow.md#available-properties-in-spel-context)

* **Form flow conditional next step**

  A next step in a form flow can now be conditional. This allows for more complex form flows. More information can be
  found [here](/using-valtimo/form-flow/create-form-flow-definition.md)

* **Search field path validation**

  A user that is configuring a SearchField will now get a validation error when the `path` field of a search field
  does not point to a property inside the document.

## Bugfixes

The following bugs were fixed:

* **Bug1**

  Description of what the issue was.

* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Form flow submission data type has been changed**

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
