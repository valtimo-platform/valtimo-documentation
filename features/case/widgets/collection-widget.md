# Collection widget

{% hint style="info" %}
This page requires:

* Basic knowledge of JSON file structure.
{% endhint %}

## Configure widget

A collection widget can be used when arrays (lists) are stored in the case data structure and need to be presented as such in the case UI. The following fields need to be configured for a collection widget.

* **Widget title**\
  \&#xNAN;_The widget title is presented in the UI at the top-left corner of the widget and should describe the content for that widget._
* **Number of cards per page**\
  \&#xNAN;_If the content exceeds the number of rows pagination will be added in the UI._
* **Path to collection data**\
  \&#xNAN;_The exact path in the JSON document that contains the array with data._
* **Card title display type**\
  Same as each text field, the title of the card can also be set to a certain [display type](fields-widget.md#display-types).

### Configure card

For each card in the collection the following configurations needs to be done.

* **Card title**\
  \&#xNAN;_The title of each card can be set to a value from the array items._\
  &#xNAN;_&#x53;o the card title is not a label in this case, but a value from a array item._
* **Display type**\
  \&#xNAN;_Select the way the card title is presented in the UI._\
  &#xNAN;_&#x50;lease find the available display types below._

### Configure card fields

A set of fields can be configured that will display the data for each card.\
The following configuration needs to be done to add a field to a card.

* **Title**\
  \&#xNAN;_Will be displayed as the fields label in the UI._
* **Value**\
  &#xNAN;_&#x54;he value itself will not actually be configured, the path targeting the value in the JSON document is configured. The value is passed through by the widget._
* **Display type**\
  \&#xNAN;_Select the way the data is presented in the UI._\
  &#xNAN;_&#x50;lease find the available display types below._
* **Field width**\
  \&#xNAN;_For each field the choice can be made to use the full width of the card or half._

{% hint style="info" %}
**Display types**\
The [same list of display types](fields-widget.md#display-types) is available as for the fields widget.\
Please find the documentation on the different display types there.
{% endhint %}

{% hint style="info" %}
**Collection widget configuration example**

Below example shows the configuration for a collection that displays uploaded files.\
Each card in the collection will get it's title and the card fields from the array data.\
\
The card name will be set to the file name.\
The card fields will show following information:

* Created on
* Storage bucket
* Size (in bytes)\\

**The path in the JSON document for the array:**\
`doc:/uploadedFiles`

\
**The information from the array that is shown:**

Since the location of the array itself is known it is no longer need to define a full JSON path for the values of the card fields. Only define the data location within the array like so:\
\
**Card title:**\
`data/name`\
\
**Card fields:**

`data/createdOn`

`data/storageBucket`

`data/sizeInBytes`

\
To gather the data the widget code will combine the "Path to collection data" field with the value fields from the card configuration. This results in the following JSON paths where x is filled by iterating over the array data.

`doc:/uploadedFiles[x]/data/name`

`doc:/uploadedFiles[x]/data/createdOn`

`doc:/uploadedFiles[x]/data/storageBucket`

`doc:/uploadedFiles[x]/data/sizeInBytes`

\
This configuration is based on below JSON.\
The uploadedFiles object exists in the root of this JSON document.\
\
Below the JSON a screenprint of the configuration in the Widget configuration UI.
{% endhint %}

```json
"uploadedFiles": [ 
  {
    "data": { 
      "key": "Upload Test-22b44a2f-9790-4730-b2bf-d8f017711046.docx", 
      "name": "Upload Test.docx",
      "createdOn": "2024-10-30T07:15:33.121Z",
      "bucketName": "exampleBucket",
      "resourceId": "85a1b768-41b4-4f62-adbc-40dcbe0e7adf",
      "sizeInBytes": 12668 
    },
    "size": 12668,
    "type": "docx",
    "storage": "url",
    "customUpload": true,
    "originalName": "Upload Test.docx"
  } 
]
```

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption><p>Uploaded files collection widget configuration</p></figcaption></figure>

### Presentation in the UI

See below screenshot for the presentation result of a collection. 6 files where uploaded for this example so 3 pages of each 2 cards are shown in the widget.\
\
![](<../../../.gitbook/assets/image (27).png>)
