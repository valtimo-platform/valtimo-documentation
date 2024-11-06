# Table widget

{% hint style="info" %}
This page requires:

* Basic knowledge of JSON file structure.
{% endhint %}

## Configure widget

A table widget can be used when arrays (lists) are stored in the case data structure and need to be presented as such in the case UI. The following fields need to be configured for a table widget.

* **Widget title**\
  _The widget title is presented in the UI at the top-left corner of the widget and should describe the content for that widget._
* **Rows per page**\
  _If the content exceeds the number of rows pagination will be added in the UI._
* **Path to table data**\
  _The exact path in the JSON document that contains the array with data._
* **Table columns**\
  _Columns need to be based on the available fields within the array data._\


### Configure table columns

For each column in the table the following configurations needs to be done.

* **Title**\
  _The title will be displayed as the label of the field in the widget._
* **Value**\
  _The value itself will not actually be configured, the path targeting the value in the JSON document is configured. The value is passed through by the widget._
* **Display type**\
  _Select the way the data is presented in the UI._\
  _Please find the available display types below._

{% hint style="info" %}
The [same list of display types](fields-widget.md#display-types) is available as for the fields widget.\
Please find the documentation on the different display types there.
{% endhint %}

{% hint style="info" %}
**Table widget configuration example**

Below example shows the configuration for a table that displays uploaded files by there name and creation date.

**The path in the JSON document for the array:**\
`doc:/uploadedFiles`

\
**The information from the array that is shown:**

Since the location of the array itself is known it is no longer need to define a full JSON path for the values of the table columns. Only define the data location within the array like so:\
`data/name`

`data/createdOn`

\
To gather the data the widget code will combine the "Path to table data" field with the value fields from the column configuration. This results in the following JSON paths where x is filled by iterating over the array data.

`doc:/uploadedFiles[x]/data/name`

`doc:/uploadedFiles[x]/data/createdOn`

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
      "bucketName": "exampleFiles",
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

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Uploaded files table widget configuration</p></figcaption></figure>

### Table widget options

Below option there is a toggle available named "_First column is the title of the row"_. Enabling this will display the first column with italics and no underline. See below screenshots for the difference in presentation in the result of above configuration. 6 files where uploaded for this example so 3 pages of each 2 files are shown in the widget.\


<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption><p>Uploaded files with first column set as title column</p></figcaption></figure>
