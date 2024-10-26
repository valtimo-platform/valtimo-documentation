# List

On the **List** tab of the Case Definition, the columns displayed in the list of cases presented to end users in the Valtimo UI can be configured. When a case type is selected from the **Cases** menu, the list screen opens and displays all cases of that type in a list according to this configuration.

{% hint style="info" %}
If no configuration exists for a case, Valtimo defaults to the following list of case metadata:

* Reference number
* Created by
* Created on
* Last modified
* Assignee (only if configured)
* Status (only if configured)
{% endhint %}



## List field types

Overview of available configuration fields and the corresponding field types.

* **Title**\
  The title is an optional field that appears as the label in the search field case list UI. This field is not mandatory and if left blank a translation of the Key will be shown. If no translation for the Key is set, the Key will be shown.\

* **Key**\
  This field needs to be unique within this case, submission will be prevented if duplicates are found.\

* **Path**\
  The path input gives access to the data fields and meta data of the case. These can easily be identified by there prefix. Case data can be targeted by using the **doc:** prefix. Use the **case:** prefix to target the case meta data.

{% hint style="info" %}
**Prefix examples**\
\
**Path:** case:assigneeFullname\
_This path targets the assigned case handlers full name._\
\
**Path:** doc:request.budget\
_This path targets the case data itself. The doc: prefix directs to the content object of the case document so the same JSON paths that where used in the formIO forms to store the data._
{% endhint %}

* **Display Type**\
  With this setting the behavior of the UI in the list overview can be set. Data can be displayed as normal text, but also as dates, booleans, or tags for example. Try out the types to see what works for each case.\

* **Sortable** and **Default Sort**\
  If set the header column will have the sort options available for this column, default sort setting is executed on page enter. A default sort order can be selected when Sortable is checked.

## Configure case list

To configure the columns of the case list overview the same type of prefixes can be used as for the search fields configuration.

{% tabs %}
{% tab title="Via UI" %}
Click on `Cases` in the Admin menu and select the `List` tab.

Click on the **Add column +** button on the top right to configure a new column.

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

With help from the List field types information on the top of this page each column can be configured. The Save button becomes available once all mandatory fields are configured.

{% hint style="info" %}
The first column added to a configuration immediately disables all default metadata columns. As a result, only the configured column will be displayed in the user interface.
{% endhint %}


{% endtab %}

{% tab title="Via IDE" %}

{% endtab %}
{% endtabs %}

