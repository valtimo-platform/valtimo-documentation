# Case widgets tab
A case widgets tab provides the user with an overview of data that is related to the case by using standard or custom components.
These tabs can be configured by an administrator or developer, where widgets can be added and configured to show fields in a specific way.

Multiple tabs can be configured to support several user roles in their daily work. Visibility of tabs and widgets can be controlled via the authorization layer.

## Configuration

### Autodeployment
> **Note**: A tab of type `widgets` should be added first, please follow [these instructions](../case-tabs.md#auto-deploying-case-tabs). 

Case widget tabs can be autodeployed by adding json files on the classpath.
These files should end with `.case-widget-tab.json` to be eligible for autodeployment.

Every deployment file represents a changeset. These files are required to contain a `changesetId` that should be unique
over all deployment files that use changesets. When starting up, changesets that have already been executed will be ignored.
A checksum of the changeset is created when it is executed. Changesets that have already been deployed should not change.
Changesets that have been changed since a previous time will result in an error and failure to start the application.

All changesets can be executed again, even when the content has changed, by setting the `valtimo.changelog.case-widget-tab.clear-tables` property to `true`. This also deletes all existing case tab widgets.
By default, this setting is disabled.

**my-case.case-task-list.json**:
```json
{
  "changesetId": "case-widget-tab-v1",
  "tabs": [
    {
      "caseDefinitionName": "bezwaar",
      "key": "widgets",
      "widgets": [
        {
          "key": "my-fields",
          "type": "fields",
          "title": "My fields",
          "width": 4,
          "highContrast": true,
          "properties": {
            "columns": [
              [
                {
                  "key": "firstName",
                  "title": "First name",
                  "value": "doc:firstName"
                },
                {
                  "key": "partner",
                  "title": "Partner",
                  "value": "doc:partner.name"
                },
                {
                  "key": "active",
                  "title": "Active",
                  "value": "doc:active",
                  "displayProperties": {
                    "type": "boolean"
                  }
                },
                {
                  "key": "length",
                  "title": "Length",
                  "value": "doc:length",
                  "displayProperties": {
                    "type": "number",
                    "digitsInfo": "1.0-0"
                  }
                }
              ],
              [
                {
                  "key": "dateOfBirth",
                  "title": "Date of birth",
                  "value": "doc:dateOfBirth",
                  "displayProperties": {
                    "type": "date",
                    "format": "DD-MM-YYYY"
                  }
                },
                {
                  "key": "gender",
                  "title": "Gender",
                  "value": "doc:partner.gender",
                  "displayProperties": {
                    "type": "enum",
                    "values": {
                      "m": "Male",
                      "f": "Female",
                      "x": "Other"
                    }
                  }
                },
                {
                  "key": "income",
                  "title": "Income",
                  "value": "doc:income",
                  "displayProperties": {
                    "type": "currency",
                    "currencyCode": "EUR",
                    "display": "symbol",
                    "digitsInfo": "1.0-0"
                  }
                },
                {
                  "key": "fulltimePercentage",
                  "title": "Full-time percentage",
                  "value": "doc:fulltimePercentage",
                  "displayProperties": {
                    "type": "percent",
                    "digitsInfo": "1.0-0"
                  }
                },
              ]
            ]
          }
        },
        {
          "key": "my-table",
          "type": "table",
          "title": "My table",
          "width": 4,
          "highContrast": false,
          "properties": {
            "collection": "doc:people",
            "defaultPageSize": 2,
            "columns": [
              {
                "key": "firstName",
                "title": "First name",
                "value": "doc:firstName"
              },
              {
                "key": "partner",
                "title": "Partner",
                "value": "doc:partner.name"
              },
              {
                "key": "active",
                "title": "Active",
                "value": "doc:active",
                "displayProperties": {
                  "type": "boolean"
                }
              },
              {
                "key": "length",
                "title": "Length",
                "value": "doc:length",
                "displayProperties": {
                  "type": "number",
                  "digitsInfo": "1.0-0"
                }
              }
            ]
          }
        }
      ]
    }
  ]
}


```



