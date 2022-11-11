# Frontend libraries 5.14.0 (RC)

## New Features

The following features were added:

* **Download case search fields configuration**

  If the `caseSearchFields` feature toggle is enabled, a 'Search Fields' tab is shown on the Case details page
  (i.e. Admin -> Cases -> Leningen). On this tab, a 'Download search field configuration' button is now shown, which
  downloads the search field configuration for the current document type as a JSON file.

  For more information on how to enable the `caseSearchFields` feature toggle, refer to [this page](/reference/feature-toggles/available-feature-toggles.md).

## Bugfixes

The following bugs were fixed:

* **Enum BooleanTypeConverter**

  Fixed the ability to provide custom values enum to BooleanTypeConverter.
  An example how this can be configured in environment as a property in a DefinitionColumn.

  `{
  propertyName: '$.isPropertyTrue',
  translationKey: 'isPropertyTrue',
  sortable: true,
  viewType: 'boolean',
  enum: ['Ja', 'Nee']
  },`

  The enum property only accepts maximum two string values where the first one is for true and the second one is for false. 

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
