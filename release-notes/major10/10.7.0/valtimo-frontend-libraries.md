# Frontend libraries 10.7.0

## New Features

The following features were added:

**Added edit note and delete note options on the notes tab**

Added the functionality to edit and delete a note in an order. It can only be edited if the text field is not empty.

* **Automatic User Task assignment to Case Handler**

  An additional checkbox has been added to the case assignee section of a case configuration that enables the user to 
  toggle on and off the automatic assignment of user tasks to a case handler if a case has one assigned to it/is 
  claimed by one.  
  Refer [to this page](/using-valtimo/document/automatic-task-assignment.md) to learn more about this feature.

* **Carbon breadcrumbs and page title**

  New breadcrumbs and page titles have been introduced throughout the application, in order to provide a consistent user
  experience with Carbon components. Since previously URLs and breadcrumbs were not implemented consistently, some
  logic had to be introduced in order to provide proper breadcrumbs. How this was implemented, and how to use this logic
  in your implementation, is explained on [this page](/reference/user-interface/breadcrumbs.md).

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