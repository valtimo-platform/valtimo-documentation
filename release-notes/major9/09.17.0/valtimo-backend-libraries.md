# Backend libraries 9.17.0 RC

## New Features

The following features were added:

* **Improved DocumentVariableDelegateImpl**

  The `findValueByJsonPointer` method of the `DocumentVariableDelegateImpl` class
  now returns a collection of elements instead of throwing an exception
  when the node is an ArrayNode.


* **Postgres support**

  Almost all modules within Valtimo now have support for Postgres databases. The exceptions are:
  - `form-flow-valtimo`
  
  Information on how to use Postgres can be found [here](/valtimo-implementation/database-support.md).


* **Secret keys in plugins are encypted before storing**

  Properties in plugins can now be marked as secret. When configuring the plugin the secrets will be encrypted before 
  being stored.
  
  More information on plugin secrets can be found [here](/extending-valtimo/plugin/custom-plugin-definition.md#plugin-properties).


## Bugfixes

The following bugs were fixed:

* **Changeset errors on Liquibase 4.8.0 and higher**

  `foreignKeyTableName` is required for `foreignKeyConstraintExists` on Liquibase 4.8.0 and higher. Existing changesets did not implement this property.

## Breaking changes

No known breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
