# Widget display types

The display types listed below are the ones that are included in Valtimo.&#x20;

Each display type used must be imported in the `AppModule` of your front-end implementation if you want to use them. They are exported from `'@valtimo/dashboard'`.

## Number

Key: `number`

Front-end module: `BigNumberModule`

Displays the data as a single number in text.

<div align="center" data-full-width="false"><img src="../../reference/modules/img/display-type-number-example.png" alt="Example of display type &#x27;number&#x27;"></div>

### Properties

| Name                      | Description                                                                                                                                                                                                                        |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `title`                   | The title of the widget, shown at the top of the widget.                                                                                                                                                                           |
| `subtitle`                | The text shown below the title.                                                                                                                                                                                                    |
| `label`                   | The label that is displayed to the right of the number. Can be used to clarify what the number indicates.                                                                                                                          |
| `useKPI`                  | Enables the use of thresholds to change the color of the number. When set to `false` the color of the number is black. When set to `true` the color of the number is green unless it is above one or more of the threshold values. |
| `lowSeverityThreshold`    | Limit above which the color of the number becomes yellow.                                                                                                                                                                          |
| `mediumSeverityThreshold` | Limit above which the color of the number becomes orange.                                                                                                                                                                          |
| `highSeverityThreshold`   | Limit above which the color of the number becomes red.                                                                                                                                                                             |

## Donut chart

Key: `donut`

Front-end module: `DonutModule`

Displays multiple counts in a donut chart.

<div align="center"><figure><img src="https://v1.docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F181910120-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FG21VIGcgPc1cyGRZY5CR%252Fuploads%252Fgit-blob-842a6fe7e0482e282105063e93a0e8d732c4c888%252Fdisplay-type-donut-example.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=a06a18a1&#x26;sv=2" alt=""><figcaption><p>Example of display type 'donut chart'</p></figcaption></figure></div>

### **Properties**

| Name       | Description                                                        |
| ---------- | ------------------------------------------------------------------ |
| `title`    | Required. The title of the widget, shown at the top of the widget. |
| `subtitle` | The text shown below the title.                                    |
| `label`    | The label that is displayed in the center of the donut.            |

## Meter chart <a href="#meter-chart" id="meter-chart"></a>

Key: `meter`

Front-end module: `MeterModule`

Displays multiple counts in a horizontal meter chart.

<figure><img src="https://v1.docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F181910120-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FG21VIGcgPc1cyGRZY5CR%252Fuploads%252Fgit-blob-78ca3165ec8c07c7b4f5ea56b3d1e9cfd9d33de0%252Fdisplay-type-meter-example.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=ce14f3d6&#x26;sv=2" alt=""><figcaption><p>Example of display type 'meter chart'</p></figcaption></figure>

### **Properties**

| Name       | Description                                                        |
| ---------- | ------------------------------------------------------------------ |
| `title`    | Required. The title of the widget, shown at the top of the widget. |
| `subtitle` | The text shown below the title.                                    |

## Gauge <a href="#gauge" id="gauge"></a>

Key: `gauge`

Front-end module: `GaugeModule`

Displays a count and a total count in a gauge.

<figure><img src="https://v1.docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F181910120-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FG21VIGcgPc1cyGRZY5CR%252Fuploads%252Fgit-blob-698884b17edc61963ee87c834bf9de262f271c25%252Fdisplay-type-gauge-example.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=5d896d6e&#x26;sv=2" alt=""><figcaption><p>Example of display type 'gauge'</p></figcaption></figure>

### **Properties**

| Name       | Description                                                                              |
| ---------- | ---------------------------------------------------------------------------------------- |
| `title`    | Required. The title of the widget, shown at the top of the widget.                       |
| `subtitle` | The text shown below the title.                                                          |
| `label`    | The label specifies the type of item under the gauge. In the screenshot this is 'zaken'. |
