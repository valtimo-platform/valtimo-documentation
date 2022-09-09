# Custom case columns

Each case comes with a default case overview with four standard columns. 'Reference number', 'Created by', 'Created on',
and 'Last modified'. These columns can be adjusted. Any key defined in a document can be used as a column in a case
overview.

| <!-- -->                                                      |
|---------------------------------------------------------------|
| ![Default case detail list](img/default-case-detail-list.png) |
| <center>Default case overview</center>                        |

## Default columns

In the environment file, the following default inline code is found for the case overview columns:

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

...
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

...
  ```

For each case for which custom columns are to be defined, an array is added with the desired columns. The document
definition id is used as a key to point to this array, i.e.:  `'document-definition-name': []`.

In this array, for each column an object is added with the following properties:

- `propertyName`: The key from the document definition that is to be used to display column data. Default properties
like `sequence` can be written plainly. Properties nested inside like `firstName` use a `$.` notation, i.e.: 
`$.firstName`.
- `translationKey`: The path to a translation in the translation files. In the above example, a combination of the
document definition name and the key from the document definition is used.
- `sortable`: A `boolean` value, which states whether the column should be sortable. Only enable this if the back-end
supports sorting on this property.
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

...
  ```

## Translations

In order to add translations for the column headers, navigate to the translation resource files in your implementation
(like `en.json` and `en.json`) and add all your column translation keys under the `fieldLabels` key:

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