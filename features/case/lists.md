# Lists

To configure the columns of the case list overview the same prefixes can be used as described above for the search fields configuration.

<div align="left">

<figure><img src="../../.gitbook/assets/image (21).png" alt="" width="563"><figcaption><p>Add case list view column</p></figcaption></figure>

</div>

* **Title**\
  The title is an optional field that appears as the label in the search field case list UI. This field is not mandatory and if left blank a translation of the Key will be shown. If no translation for the Key is set, the Key will be shown.\

* **Key**\
  This field needs to be unique within this case, submission will be prevented if duplicates are found.\

* **Path**\
  The path input gives access to the data fields and meta data of the case. These can easily be identified by there prefix. Case data can be targeted by using the **doc:** prefix. To target the meta data of the use the **case:** prefix.\

* **Display Type**\
  With this setting the behaviour of the UI in the list overview can be set. Data can be displayed as normal text, but also as dates, booleans, or tags for example. Try out the types to see what works for each case.\

* **Sortable** and **Default Sort**\
  If set the header column with have the sort options available for this column, default sort setting is executed on page enter.
