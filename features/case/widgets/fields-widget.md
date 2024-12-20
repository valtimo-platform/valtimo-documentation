# Fields widget

To create a fields widget the following configurations need to be done.

## Configure widget

* **Widget title**\
  &#xNAN;_&#x54;he widget title is presented in the UI at the top-left corner of the widget and should describe the content for that widget._
* **Configure widget fields**\
  &#xNAN;_&#x45;ach field can be configured to display case data in a certain way._

### Configure widget fields

For each field that is added to the widget the following configuration is required in order to display the data correctly in the UI.

* **Field title**\
  &#xNAN;_&#x54;his is presented as the label of the field_
* **Field value**\
  &#xNAN;_&#x41;dd the exact path to the data in the JSON document._
* **Display type**\
  &#xNAN;_&#x53;elect the way the data is presented in the UI._\
  _Please find the available display types below._

### Display types

The following display types are supported in the case widgets configuration.

<table><thead><tr><th width="171">Display type</th><th>Presentation</th></tr></thead><tbody><tr><td>Text</td><td>Value is presented in the UI as regular text.</td></tr><tr><td>Yes/No</td><td>This converts a Boolean value to "Yes"/"No".</td></tr><tr><td>Date</td><td>Accepts a UTC date string as input. A format can be specified for how you wish the date to be displayed (this is optional).</td></tr><tr><td>Number</td><td>The number display type is based on the DecimalPipe* from Angular.<br>Optional formatting can be specified for how you wish the number to be displayed.<br><br></td></tr><tr><td>Percentage</td><td>The percentage display type is based on the PercentPipe* from Angular.<br>Optional formatting can be specified for how you wish the percentage to be displayed.<br><br>By default any value is divided by 100, unless a format is specified. This has been done because of the values that the Angular PercentPipe* expects.</td></tr><tr><td>Currency</td><td>The currency display type is based on the CurrencyPipe* from Angular. Optional formatting can be specified for how you wish the currency to be displayed.</td></tr><tr><td>Enum</td><td>Enum (or enumerate) is meant to assign a value to a key as to display data more accurately. The key is stored in the JSON document, the value is configured in the enum, based on the key the corresponding value is displayed.</td></tr></tbody></table>



{% hint style="info" %}
Below descriptions are from the following Angular documentation pages:

* [https://v17.angular.io/api/common/DecimalPipe](https://v17.angular.io/api/common/DecimalPipe#digitsinfo)
* [https://v17.angular.io/api/common/PercentPipe](https://v17.angular.io/api/common/PercentPipe)
* [https://v17.angular.io/api/common/CurrencyPipe](https://v17.angular.io/api/common/CurrencyPipe)
{% endhint %}

#### \*Angular DecimalPipe

The value's decimal representation is specified by the `digitsInfo` parameter, written in the following format:

```
{minIntegerDigits}.{minFractionDigits}-{maxFractionDigits}
```

* `minIntegerDigits`: Minimum number of integer digits before the decimal point. Default is 1.
* `minFractionDigits`: Minimum number of digits after the decimal point. Default is 0.
* `maxFractionDigits`: Maximum number of digits after the decimal point. Default is 3.

If the formatted value is truncated it will be rounded using the "to-nearest" method:

```
{{3.6 | number: '1.0-0'}}
<!--will  '4'-->

{{-3.6 | number:'1.0-0'}}
<!--will  '-4'-->
```

#### \*Angular PercentPipe

Decimal representation options, specified by a string in the following format:\
`{minIntegerDigits}.{minFractionDigits}-{maxFractionDigits}`.

* `minIntegerDigits`: Minimum number of integer digits before the decimal point. Default is `1`.
* `minFractionDigits`: Minimum number of digits after the decimal point. Default is `0`.
* `maxFractionDigits`: Maximum number of digits after the decimal point. Default is `0`.

#### \*Angular CurrencyPipe

The format for the currency indicator. One of the following:

* `code`: Show the code (such as `USD`).
* `symbol`(default): Show the symbol (such as `$`).
* `symbol-narrow`: Use the narrow symbol for locales that have two symbols for their currency.\
  For example, the Canadian dollar CAD has the symbol `CA$` and the symbol-narrow `$`.\
  If the locale has no narrow symbol, uses the standard symbol for the locale.
* String: Use the given string value instead of a code or a symbol.\
  For example, an empty string will suppress the currency & symbol.
* Boolean (marked deprecated in v5): `true` for symbol and false for `code`.



### Widget columns

The fields widget is also able to display data on multiple columns. As such a column can be added or removed. However you cannot have more columns than the width of the widget (For example, if a widget has a width set to _Medium_ you cannot add more than 2 columns to it)

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>
