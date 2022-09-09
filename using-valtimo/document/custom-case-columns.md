# Custom case columns

Each case comes with a default case list with four standard columns. 'Reference number', 'Created by', 'Created on',
and 'Last modified'. The columns in the list can be changed, added and removed. Any key defined in a document can be
used as a column in a case list.

| <!-- -->                                                      |
|---------------------------------------------------------------|
| ![Default case detail list](img/default-case-detail-list.png) |
| <center>Default case list</center>                            |

## Default columns

In the environment file, the following default inline code is found for the case list columns. This defines the columns
that will be used in the case list, unless a custom column set has been configured for that case type.

#### **`environment.ts`**
  ```typescript
...

const defaultDefinitionColumns: Array<DefinitionColumn> = [
    {
        propertyName: 'sequence',
        translationKey: 'referenceNumber',
        sortable: true,
    },
    {
        propertyName: 'createdBy',
        translationKey: 'createdBy',
        sortable: true,
    },
    {
        propertyName: 'createdOn',
        translationKey: 'createdOn',
        sortable: true,
        viewType: 'date',
        default: true,
    },
    {
        propertyName: 'modifiedOn',
        translationKey: 'lastModified',
        sortable: true,
        viewType: 'date',
    },
];

...

export const environment: ValtimoConfig = {
    ...
    defaultDefinitionTable: defaultDefinitionColumns,
    ...
};
  ```

## Custom columns

This above code can be used as a basis for custom columns. First add the line `customDefinitionTables: {}` below the
line `defaultDefinitionTable: defaultDefinitionColumns`:

#### **`environment.ts`**
  ```typescript
...

export const environment: ValtimoConfig = {
    ...
    defaultDefinitionTable: defaultDefinitionColumns,
    customDefinitionTables: {}
    ...
};
  ```

Inside the brackets custom columns can then be defined:

#### **`environment.ts`**
  ```typescript
...

export const environment: ValtimoConfig = {
    ...
    defaultDefinitionTable: defaultDefinitionColumns,
    customDefinitionTables: {
        'document-definition-name' : [
            {
                propertyName: '$.firstName',
                translationKey: 'document-definition-name.firstName',
                sortable: false,
                viewType: 'string',
                default: true
            },
            {
                propertyName: 'modifiedOn',
                translationKey: 'lastModified',
                sortable: true,
                viewType: 'date'
            }
        ]
    }
    ...
};
  ```

For each case for which custom columns are to be defined, an array is added with the desired columns. The document
definition id is used as a key to point to this array, i.e.:  `'document-definition-name': []`.

In this array, for each column an object is added with the following properties:

- `propertyName`: The key from the document definition that is to be used to display column data. Default properties
like `sequence` can be written plainly. Document content can be accessed by referring to properties by their JSON path.
For example a `firstName` field in the root of the document can be displayed by using the expression `$.firstName`.
- `translationKey`: The path to a translation in the translation files. In the above example, a combination of the
document definition name and the key from the document definition is used.
- `sortable`: A `boolean` value, which states whether the column should be sortable. Only enable this if the back-end
supports sorting on this property. Currently, the back-end supports sorting on `createdOn`, `modifiedOn`, `sequence` and
all JSON path expressions on the content.
- `viewType`: This value is optional, and refers to the type converter to be used for the property value, otherwise the
value will be displayed as a string. Examples of available type converters are `'date'`, `'boolean'`, `'relatedFiles `
- and `'string'`.
- `default`: Only one of the columns in the array of columns can have this property. If set to `true`, on opening the
case overview, the table is sorted on this property descendingly. The sort direction may also be specified specifically
by setting this property value to `'ASC'` or `'DESC'`.

In case you want to extend on the default columns for a set of custom columns, they can be included like this:

#### **`environment.ts`**
  ```typescript
...

export const environment: ValtimoConfig = {
    ...
    defaultDefinitionTable: defaultDefinitionColumns,
    customDefinitionTables: {
        'document-definition-name' : [
            ...defaultDefinitionColumns,
            {
                propertyName: '$.firstName',
                translationKey: 'document-definition-name.firstName',
                sortable: false,
                viewType: 'string',
            }
        ]
    }
    ...
};
  ```

## Translations

In order to add translations for the column headers, navigate to the translation resource files in your implementation
(like `en.json` and `nl.json`) and add all your column translation keys under the `fieldLabels` key:

#### **`en.json`**
  ```json
{
  ...
  "fieldLabels": {
    ...
    "document-definition-name": {
      "firstName": "First name"
    }
  },
  ...
}
  ```