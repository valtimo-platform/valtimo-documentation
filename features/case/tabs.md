# Tabs

Each case in Valtimo can be configured with a specific set of case tabs. Valtimo includes a standard set of tabs preconfigured for each case, which can be customized to meet specific case requirements. Standard tabs can be removed from the tab configuration, but they can also be easily re-created through the user interface (UI). In addition to the standard tabs, custom tabs can be added to the case tab configuration to provide further customization.

## Configuring case tabs

{% tabs %}
{% tab title="Via UI" %}
* Go to the `Admin` menu
* Go to the `Cases` menu and select the case you want to configure
* Select the `Tabs` tab
* Click on **Add tab**

The standard Valtimo case tabs for each new case are listed below. Standard tabs can be deleted as needed, as they can be easily re-added using the **Add tab** button.

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

The **Add tab** button opens the _Add new tab in \<case>_ modal, beginning with the configuration step to select the tab type. In this modal, **standard tabs** are available and next to this a **Form.io**, **Custom** or **Widget component** can be configured as a case tab.

* Click on the **Add tab** button.
*   Select which tab type you want to configure.\


    <figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Case tab types</p></figcaption></figure>

### Standard tab

The standard tab option is only available if all standard tabs have not yet been added to the case. When all standard tabs are already included in a case definition, this option will appear grayed out. In the modal to configure a standard tab, a dropdown menu displays the available standard tabs for selection and configuration.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption><p>Selectable standard case tabs</p></figcaption></figure>

**Tab name (optional)**\
&#xNAN;_&#x43;onfigured name that will be used to identify the Case tab in the UI._

{% hint style="info" %}
This field is not mandatory and if left blank a translation of the key will be shown if configured. Each tab name follows this logic:

1. Show the Tab name if configured
2. Get the translation for the key if available
3. Display the key
{% endhint %}

**Key**\
&#xNAN;_&#x54;his is the identifier of the tab and needs to be unique within a case definition._\
_Possible translations need to be configured with this key._

**Choose standard content**\
&#xNAN;_&#x41; list of available standard tabs is presented in a dropdown menu._\
_Already configured tabs are filtered from this list._

**Task list visible on tab**\
&#xNAN;_&#x57;hen set the task list will be displayed on the right side of the tab in the UI._\


### Form.io component

This component type makes it possible to select any Form.io form within the implementation.\
Configurable options are exact the same as for a standard tab except for selecting the component. Now a dropdown menu is shown with all available Form.io forms that exists within the implementation.

### Custom component

The Custom component button gives access to the available custom components within the Valtimo implementation. Custom components need to be added to the codebase via plugins or implementation specific code. Once added to the codebase these will become available in this modal to configure as a tab.

### Widgets component

The widgets component makes it possible to configure a case tab with widgets that can be  configured via the UI. Multiple widget types are available to present case data.\
When a widgets component is selected only the **Tab name**, **Key** and **task list visibility** can be configured for the tab.

{% hint style="info" %}
When a widgets component tab is added the tab will be listed as a configured tab.\
Normally when an item in the list is clicked the tab configuration modal opens.\
A widget type tab however opens the widget configuration when clicked.\
Tab configuration is still available by clicking the 3-dotted (kebab) menu on the far right of each item in the list and click `Edit`.
{% endhint %}

Below a screenshot of the widget configuration UI for a newly created widgets tab. This page opens when a widget type tab is clicked on the tab configuration page.

For widget configuration, check [this page](widgets/).

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Widget configuration UI</p></figcaption></figure>
{% endtab %}

{% tab title="Via IDE" %}
Case tabs can be auto-deployed from a JSON file at startup. This is useful to keep the case tab configuration identical across multiple environments. Case tabs are auto-deployed by scanning files on the classpath that end in `.case-tabs.json`.

#### Changesets <a href="#changesets" id="changesets"></a>

Every deployment file for represents a changeset. These files are required to contain a changesetId that should be unique over all deployment files that use changesets. When starting up, changesets that have already been executed will be ignored. A checksum of the changeset is created when it is executed. Changesets that have already been deployed should not change. Changesets that have been changed since a previous time will result in an error and failure to start the application.

All changesets can be executed again, even when the content has changed, by setting the `valtimo.changelog.case-tabs.clear-tables` property to `true`.

#### Example <a href="#example" id="example"></a>

You can find an example of the JSON below.

In this example a tab is created with type `standard`. Different tab types can be used to customize the tab.&#x20;

```json
{
  "changesetId": "my-case-definition-name-tabs-v1",
  "case-definitions": [
    {
      "key": "my-case-definition-name",
      "tabs": [
        {
          "name": "Summary",
          "key": "summary",
          "type": "standard",
          "contentKey": "summary"
        },
        {
          "name": "Progress",
          "key": "progress",
          "type": "standard",
          "contentKey": "progress"
        },
        {
          "name": "Zaak objects",
          "key": "zaakobjecten",
          "type": "standard",
          "contentKey": "zaakobjecten"
        }
      ]
    }
  ]
}
```

## Disabling case tabs

Case tabs are enabled by default since Valtimo 12. This feature can be disabled with a feature toggle in the front-end implementation. Set the `enableTabManagement` feature toggle to `false` to disable the ability to add tabs next to the Valtimo standard case tabs.\
For more information on available feature toggles, visit [this page](../../running-valtimo/application-configuration/feature-toggles.md).
{% endtab %}
{% endtabs %}

## Case tab types

Valtimo supports the following types of case tabs.

<table><thead><tr><th width="138">Type</th><th width="130">Type key</th><th>Description</th></tr></thead><tbody><tr><td><strong>Standard</strong></td><td>standard</td><td>A collection of tabs is available to support various Valtimo features. These tabs include options for displaying a summary form, viewing an audit log, and displaying the current state of the BPMN process. The available tabs are listed below.</td></tr><tr><td><strong>Form.io</strong></td><td>formio</td><td>Form.io tabs can be configured to display a Form.io form as the tab content. These tabs are intended solely for information display, as there is no functionality to submit data from these tabs, even if a submit button is included in the form definition.</td></tr><tr><td><strong>Custom</strong></td><td>custom</td><td>Custom tabs can be configured to show a custom Angular component.</td></tr><tr><td><strong>Widgets</strong></td><td>widgets</td><td>Case data, external source data, tables, collections and custom angular components can be presented on a case widget page. Each widget on a case widget tab can be configured separately.</td></tr></tbody></table>

## Standard case tabs

The following tabs are created by default for each new case in Valtimo. These case tabs are standard across all Valtimo editions; however, additional standard tabs may be available depending on the specific edition.

### Valtimo standard tabs

* **Summary**\
  &#xNAN;_&#x44;isplays case specific data from the case JSON document or external data sources._\
  _This page links to a specific Form.io form with the name **\<caseDefinitionKey>.summary**_
* **Progress**\
  &#xNAN;_&#x53;hows the current state of any active process and the history of all processes that have been executed while handling the case._
* **Audit**\
  &#xNAN;_&#x53;hows a log of all performed case actions. Information on who did what and when was that action done is logged and displayed on this tab._
* **Documents**\
  &#xNAN;_&#x44;isplays all files that where generated or uploaded while handling the case._
* **Notes**\
  &#xNAN;_&#x41;llows case handlers to leave case specific comments for internal use._

### GZAC edition additional tabs

* **Contact moments**\
  &#xNAN;_&#x53;hows all contact moments in the case that are registered in the_ [_contactmomenten API_](https://vng-realisatie.github.io/gemma-zaken/standaard/contactmomenten/index)_._
* **Case objects**\
  &#xNAN;_&#x4C;ists all JSON objects that are linked to the "Zaak" that is connected to the case._\
  _A "Zaak" can be created in "OpenZaak" and linked to the GZAC case._\
  _Objects connected to this "Zaak" are displayed on this tab._
