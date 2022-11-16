# Frontend libraries 5.14.0 (RC)

## New Features

The following features were added:

* **Download case search fields configuration**

  If the `caseSearchFields` feature toggle is enabled, a 'Search Fields' tab is shown on the Case details page
  (i.e. Admin -> Cases -> Leningen). On this tab, a 'Download search field configuration' button is now shown, which
  downloads the search field configuration for the current document type as a JSON file.

  For more information on how to enable the `caseSearchFields` feature toggle, refer to [this page](/reference/feature-toggles/available-feature-toggles.md).

* **Added new actions to case search field configuration**

  Creating, updating, deleting, and reordering search field rows for a document definition are now available actions.

  For more information on this feature, see [this page](/using-valtimo/document/configuring-search-fields.md).

* **Persist query parameters after Keycloak redirect**

  Previously after a redirect by Keycloak, only the main URL was restored, so that the user remained on the same page.
  To this functionality, saving and restoring of query parameters has been added. Now, after a Keycloak redirect, the
  previous query parameters will remain in place.


* **Added a new input field for case search field configuration modal**

  Add new input to configure the case search field title.

  The title is an optional field that appears as a label for the current search field. When the title is not set, 
  the default value will be the search field key translation (if there is no translation available, the original key value will be displayed).

  For more information on this feature, see [this page](/using-valtimo/document/configuring-search-fields.md).

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

## Breaking changes

No breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
