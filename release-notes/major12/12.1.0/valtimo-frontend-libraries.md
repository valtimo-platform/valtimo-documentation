# Frontend libraries 12.1.0

## New Features

The following features were added:

- **Document list updates**

  The list of documents associated with a case is now updated with the Carbon Design update.

- **ZGW tab**

  Under the Case management admin tab, there now exists a ZGW tab, whenever supported by the OpenZaak API.

- **Document list column management**

  Fields that are displayed in the document list, under case details, are now configurable. In the admin panel of a case definition, under the ZGW tab,
  the configuration list can be found. Here the number of columns, the order in which they are displayed and wether or not a default sorting is applied can be edited.

- **Document list filtering and sorting**

  Sorting and filtering has been added to the document list. Not all columns are sortable.

- **Carbon list updates**

  - The Carbon list now supports extra template data. The ColumnConfig interface in the *@valtimo/components* library now contains an *templateData* attribute that can be used.
  - The Carbon list supports a new display type called tags. More details about tags can be found [here](/reference/user-interface/components/valtimo-carbon-list/valtimo-carbon-list.md)
  - The Carbon list context menu now supports disabling items. More details about this can be found [here](/reference/user-interface/components/valtimo-carbon-list/list-with-actions.md)

- **Documenten API plugin versions**

  The Documenten API plugin now supports additional versions. Some of the versions now also enable new features inside
  Valtimo. More information can be
  found [here](/using-valtimo/plugin/documenten-api/configure-documenten-api-plugin.md#documenten-api-version).

- **Plugin modal updates**

  The modals for adding and editing a plugin now use Carbon design.

- **Document metadata modal updates**

  The modal for uploading document metadata now uses Carbon design. In addition, an option to edit document metadata has been added. Both modals now support the use of tags.

- **Carbon design updates**

  The tabs on the case detail page now use Carbon inline style tabs. In addition, the spacing in the page header has
  been adjusted.

- **Intermediate save**

  A new feature was added to user-tasks. Users can now save their progress on a form and continue later. You can enable the feature with this feature toggle `enableIntermediateSave` in your environment.ts file.

- **Additional dashboard display types, data sources and functionality**

  Three new display types and two new data sources are supported. In addition, data time expression are supported. For
  more information, refer to [this page](/reference/modules/dashboard.md)

## Bugfixes

The following bugs were fixed:

- **New user tasks don't always appear**

  When starting a case or when completing a user task, the next user task will now be shown on the summary page without
  the need of a hard refresh. There is now a 7.5 seconds long window in which new user tasks are retrieved. If any
  user tasks is created after the 7.5 seconds, it will not be shown on the summary page.


## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

When updating to 12.1, building the application might result in the following error:

```agsl
6 import moment from 'moment';
         ~~~~~~

  node_modules/moment/ts3.1-typings/moment.d.ts:784:1
    784 export = moment;
        ~~~~~~~~~~~~~~~~
    This module is declared with 'export =', and can only be used with a default import when using the 'allowSyntheticDefaultImports' flag.
```

This error can be resolved by setting the `allowSyntheticDefaultImports` property to `true` in the tsconfig.json file.