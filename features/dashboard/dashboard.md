# Widget data sources

The data sources listed below are the ones that are included in Valtimo.&#x20;

Each data source used must be imported in the `AppModule` of your front-end implementation if you want to use them. They are exported from `'@valtimo/dashboard'`.

## Case count

Key: `case-count`

Front-end module: `CaseCountDataSourceModule`

Returns the number of cases of a specific type that match the criteria have been set in the configuration.

### Properties

| Name                 | Description                                                                                                                                                                |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `documentDefinition` | Required. The key of the document definition for which cases need to be counted.                                                                                           |
| `queryConditions`    | An array of conditions that the case needs to match in order to be included in the count. Each item in the array is a query condition object described in the table below. |

### Query condition

| Name            | Description                                                                                                         |
| --------------- | ------------------------------------------------------------------------------------------------------------------- |
| `queryPath`     | The path of the variable that the condition uses to filter the count.                                               |
| `queryOperator` | The operator that the condition uses to filter the count. Available values are `!=`, `==`, `>`, `>=`, `<` and `<=`. |
| `queryValue`    | The value which the queryPath variable is checked against.                                                          |

## Multiple case counts <a href="#multiple-case-counts" id="multiple-case-counts"></a>

Key: `case-counts`

Front-end module: `CaseCountsDataSourceModule`

Returns multiple counts of cases of a specific type that match the criteria have been set for each count.

### **Properties**

| Name                 | Description                                                                                                                                                                                   |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `documentDefinition` | Required. The key of the document definition for which cases need to be counted.                                                                                                              |
| `queryItems`         | Required. Minimum of two need to be defined. Each `queryItem` requires a `label` and an array of `queryConditions`, the latter are similar to those require for the `case-count` data source. |

## Case group by <a href="#case-group-by" id="case-group-by"></a>

Key: `case-group-by`

Front-end module: `CaseGroupByDataSourceModule`

### Properties

| Name                 | Description                                                                                                                                                                                                |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `documentDefinition` | Required. The key of the document definition for which cases need to be counted.                                                                                                                           |
| `path`               | Required. The path of which the values need to be grouped. For example `case:createdBy`.                                                                                                                   |
| `queryConditions`    | Optional. An array of conditions that the case needs to match in order to be included in the counts. Each item in the array is a query condition object described in the table under `case-count`.         |
| `enum`               | Optional. An object which defines how items retrieved by the group by need to be displayed. This can be used to show technical values in a user-friendly way. For example `{"isRequired": "Is required"}`. |
