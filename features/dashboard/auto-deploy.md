# Auto deploying dashboards

Dashboards can be auto-deployed from a json file at startup. This is useful to keep the dashboard configuration identical across multiple environments. Dashboards are auto-deployed by scanning files on the classpath that end in `.dashboard.json`.

### Changesets

Every deployment file for represents a changeset. These files are required to contain a changesetId that should be unique over all deployment files that use changesets. When starting up, changesets that have already been executed will be ignored. A checksum of the changeset is created when it is executed. Changesets that have already been deployed should not change. Changesets that have been changed since a previous time will result in an error and failure to start the application.

All changesets can be executed again, even when the content has changed, by setting the `valtimo.changelog.dashboard.clear-tables` property to `true`.

### Example

You can find an example of the JSON below.

In this example a widget is created with display type `number` and data source `case-count`. Different display types and data sources can be used to customize the layout of the dashboard. The types that are available can be found on the [reference page](../../nog-een-plek-geven/reference/modules/dashboard.md).

```json
{
  "changesetId": "example-dashboard-v1",
  "dashboards": [
    {
      "key": "example-dashboard",
      "title": "Dashboard",
      "description": "This is an example dashboard",
      "order": 1,
      "widgetConfigurations": [
        {
          "key": "nr_of_cases_awaiting_customer_feedback",
          "title": "Nr of cases awaiting customer feedback",
          "dataSourceKey": "case-count",
          "dataSourceProperties": {
            "documentDefinition": "generic-case-type",
            "queryConditions": [
              {
                "queryPath": "doc:status",
                "queryOperator": "==",
                "queryValue": "AWAITING_FEEDBACK"
              }
            ]
          },
          "displayType": "number",
          "displayTypeProperties": {
            "title": "Nr of cases awaiting customer feedback",
            "subtitle": "Of type ",
            "label": null,
            "useKPI": true,
            "lowSeverityThreshold": 25,
            "mediumSeverityThreshold": 50,
            "highSeverityThreshold": 75
          }
        }
      ]
    }
  ]
}

```
