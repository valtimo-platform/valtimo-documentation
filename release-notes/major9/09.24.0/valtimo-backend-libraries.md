# Backend libraries 9.24.0 (RC)

## New Features

The following features were added:

* **Search fields**

  It is now possible to create, read, update and delete search fields for a document definition.

  For more information on using this feature see [this page](/using-valtimo/document/search-fields.md).
  
  Information about these endpoints can be found [here](/extending-valtimo/document/search-fields.md).

* **Search fields configuration deployment from resources**

  All search fields configurations placed in the resource folder are automatically deployed. More
  information can be found [here](../../../using-valtimo/document/case-search.md).

* **New Exact Plugin**

  A new plugin to setup a connection with Exact. See [here](/using-valtimo/plugin/exact/configure-exact-plugin.md) for 
  documentation.

## Bugfixes

The following bugs were fixed:

* **Form flow definition**

  When defining a form flow, the `nextStep` was ignored. This is no longer the case.

## Breaking changes

No breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
