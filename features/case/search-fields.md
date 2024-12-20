# Search fields

For each case a set of search fields can be configured. These fields will be displayed on top of the case list page within a search element. Search fields add the ability to filter cases that are displayed in the paginated list. Each search field adds the ability to filter on a specific field from the case data. This enables users to combine search fields to get the best result in the case list.

## Configuring search fields

{% tabs %}
{% tab title="Via UI" %}
An administrator is able to add, change, remove, reorder and download a file with all search fields. To see all the configured search fields go the menu `Admin > Cases` and select a specific case. Then click on the tab named `Search fields`.

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

### **Available actions**

**Create**\
Because each case holds its own set of data, search fields can be configured per case. A button to create a new search field is available at the top of the displayed search field list. A modal for filling in the data will be presented when clicking on this button. It is necessary to fill in all the required data to enable the `submit` button. The key field is specific identification data, so if the key is not unique, you will not be able to save the search field.

<figure><img src="../../.gitbook/assets/image (44).png" alt=""><figcaption><p>Modal to configure search field</p></figcaption></figure>

**Edit**\
When clicking on an entry in the list of `search fields`, a modal opens with the fields pre-filled with the selected item's data. It is possible to edit all the fields, except for the key. When clicking `submit`, the field data is automatically updated in the list.

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption><p>Modal to configure search field - prefilled</p></figcaption></figure>

**Reorder**\
At the far right next to the 3 dotted menu there are two arrow buttons for reordering the data. The line will be moved in the corresponding direction by clicking the up or down arrow button. When there is no possibility of moving the line, the reorder buttons will be disabled.

**Delete**\
At the far right of each search field in the list there is a menu under 3 dots. This menu contains the delete option. When deleting a confirmation is shown with the information that this action can't be undone.

**Download**\
A download icon is available next to the Add search field button at the top of the list.\
A JSON formatted file with all the information in the list will be downloaded.

<figure><img src="../../.gitbook/assets/image (45).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Via IDE" %}
A search field configuration file can be added to the resource folder. These configurations files are automatically deployed when the application starts.

Configuration files are only automatically deployed when they are located on this path:

`/resource/config/search/`

The name of the configuration file must match the name of the document definition. This ensures that the search field configuration is linked to the correct document definition. For example, if the name of the document definition is `profile`, the configuration file name must be:

`/resource/config/search/profile.json`

The content of the configuration file can look like this:

```json
{
  "searchFields": [
    {
      "title": "Last Name",
      "key": "customerLastName",
      "path": "doc:customer.lastName",
      "dataType": "text",
      "fieldType": "single",
      "matchType": "like"
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Using search fields

Configured search fields can be found on the list page of every case type. So in order to find the search fields click on `Cases` in the menu and then select a specific case.

The Search fields are located right above the case list columns.

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption><p>Case list screen - Search collapsed</p></figcaption></figure>

Click on the search bar to expand the view showing all the configured search fields.

<figure><img src="../../.gitbook/assets/image (40).png" alt=""><figcaption><p>Case list screen - Search expanded</p></figcaption></figure>

## Search field types

Overview of available configuration fields and the corresponding field types.\
Please find the more detailed description for each configuration field below this table.

| Search field   | Available types                                                           | Editable       |
| -------------- | ------------------------------------------------------------------------- | -------------- |
| **Title**      | Text                                                                      | _Editable_     |
| **Key**        | Text                                                                      | _Not editable_ |
| **Path**       | Text                                                                      | _Editable_     |
| **Data type**  | <p>Text<br>Number<br>Date<br>Date and time<br>Boolean</p>                 | _Editable_     |
| **Field type** | <p>Single<br>Range<br>Multi select dropdown<br>Single select dropdown</p> | _Editable_     |
| **Match type** | <p>Exact<br>Contains</p>                                                  | _Editable_     |

* **Title**\
  The title is an optional field that appears as the label in the search field case list UI.

{% hint style="info" %}
This field is not mandatory and if left blank a translation of the key will be shown if configured. Each title follows this logic:

1. Show the title if available
2. Get the translation for the key if available
3. Display the key
{% endhint %}

* **Key**\
  This field needs to be unique within this case, submission will be prevented if duplicates are found.\

* **Path**\
  The path input gives access to the data fields and meta data of the case. These can easily be identified by there prefix. Case data can be targeted by using the **doc:** prefix. To target the meta data of the use the **case:** prefix.

{% hint style="info" %}
**Example configuration for doc: and case: prefixes:**\


**Path:** _case:assigneeFullname_\
This path targets the assigned case handlers full name and will search that field when used in the UI.\
\
**Path:** _doc:request.budget_\
This path targets a property in the case data. The doc: prefix directs to the content object of the case document so the same JSON paths can be used as where used in the Form.io forms to gather the data.
{% endhint %}

* **Data type**\
  Select the correct data type for the best UI experience on the data fields that are configured.\
  In the end, everything is stored as text in JSON but by setting the correct data type a date input can be a date picker and the input can be validated.\

* **Match**\
  This let's you configure the behavior of the search. Selecting **exaxt** will only give results when the exact match is made and selecting **Contains** will return the results where the input matches part of the data.\

* **Field type**\
  Fine tune the search with the field type. Change the search field UI from Single text input to Ranged input or set a single or multi select dropdown.

{% hint style="success" %}
The best advice to learn how the search fields react to certain types of data is to try it out. Play around with the data, match and field type options to see what works for each case.
{% endhint %}
