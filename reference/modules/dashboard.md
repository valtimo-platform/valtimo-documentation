# Dashboard

The data sources and display types listed below are the ones that come included in Valtimo.  

## Data sources

### Case count

Key: `case-count`

Returns the number of cases of a specific type that match the criteria have been set in the configuration. 

#### Properties

| Name                 | Description                                                                                                                                                                |
|----------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `documentDefinition` | Required. The key of the document definition for which cases need to be counted.                                                                                           |
| `queryConditions`    | An array of conditions that the case needs to match in order to be included in the count. Each item in the array is a query condition object described in the table below. |

#### Query condition

| Name            | Description                                                                                                         |
|-----------------|:--------------------------------------------------------------------------------------------------------------------|
| `queryPath`     | The path of the variable that the condition uses to filter the count.                                               |
| `queryOperator` | The operator that the condition uses to filter the count. Available values are `!=`, `==`, `>`, `>=`, `<` and `<=`. |
| `queryValue`    | The value which the queryPath variable is checked against.                                                          |


## Display types

### Number

Key: `number`

Displays the data as a single number in text.

![Example of 'number' display type of widget](img/display-type-number-example.png)

#### Properties

| Name                      | Description                                                                                                                                                                                                                        |
|---------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `title`                   | The title of the widget, shown at the top of the widget.                                                                                                                                                                           |
| `subtitle`                | The text shown below the title.                                                                                                                                                                                                    |
| `label`                   | The label that is displayed to the right of the number. Can be used to clarify what the number indicates.                                                                                                                          |
| `useKPI`                  | Enables the use of thresholds to change the color of the number. When set to `false` the color of the number is black. When set to `true` the color of the number is green unless it is above one or more of the threshold values. |
| `lowSeverityThreshold`    | Limit above which the color of the number becomes yellow.                                                                                                                                                                          |
| `mediumSeverityThreshold` | Limit above which the color of the number becomes orange.                                                                                                                                                                          |
| `highSeverityThreshold`   | Limit above which the color of the number becomes red.                                                                                                                                                                             |
