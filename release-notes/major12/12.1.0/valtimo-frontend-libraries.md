# Valtimo frontend libraries

## New Features

The following features were added:

*   **Document list updates**

    The list of documents associated with a case is now updated with the Carbon Design update.
*   **ZGW tab**

    Under the Case management admin tab, there now exists a ZGW tab, whenever supported by the OpenZaak API.
*   **Document list column management**

    Fields that are displayed in the document list, under case details, are now configurable. In the admin panel of a case definition, under the ZGW tab, the configuration list can be found. Here the number of columns, the order in which they are displayed and wether or not a default sorting is applied can be edited.
*   **Document list filtering and sorting**

    Sorting and filtering has been added to the document list. Not all columns are sortable.
* **Carbon list updates**
  * The Carbon list now supports extra template data. The ColumnConfig interface in the _@valtimo/components_ library now contains an _templateData_ attribute that can be used.
  * The Carbon list supports a new display type called tags. More details about tags can be found [here](../../../nog-een-plek-geven/reference/user-interface/valtimo-carbon-list.md)
*   **Documenten API plugin versions**

    The Documenten API plugin now supports additional versions. Some of the versions now also enable new features inside Valtimo. More information can be found [here](../../../features/plugins/configure-documenten-api-plugin.md#documenten-api-version).
*   **Plugin modal updates**

    The modals for adding and editing a plugin now use Carbon design.

## Bugfixes

The following bugs were fixed:

*   **Bug1**

    Description of what the issue was.
*   **Bug2**

    Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**
* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

*   **Deprecation1**

    X was deprecated and is replaced with Y.
*   **Deprecation2**

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
