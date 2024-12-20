# Widgets

Widgets enable the presentation of case-specific data, either from the case's own data objects or from external data sources. This approach standardizes the display of case data across all cases and eliminates the need for knowledge of Form.io or HTML to present case data effectively.

## Configuring widgets

Widget configuration is part of tab configuration for a case definition.

* Go to the `Admin` menu
* Go to the `Cases` menu and select the case to configure widgets for
* Select the `Tabs` tab

The list of configured tabs for a case is displayed within the case settings. To configure widgets, select an existing tab with its type set to Widgets, or add a new widget-type tab to the configuration by clicking the **Add tab** button as documented [here](../tabs.md). Upon selection, the widget configuration for the chosen tab will open, displaying a list of widgets created for that tab.

<figure><img src="../../../.gitbook/assets/image (11).png" alt=""><figcaption><p>Widget configuration UI</p></figcaption></figure>

Click **Add widget** to open the create new widget modal that will guide the widget creation in 4 steps.

{% stepper %}
{% step %}
### Choose widget type

Five types of widgets are currently supported:

* **Fields**\
  &#xNAN;_&#x41; set of single data elements in a widget._
* **Custom component**\
  &#xNAN;_&#x41;n option to direct to a custom Angular component in de codebase._
* **Form.io form**\
  &#xNAN;_&#x54;his type makes is possible to display a Form.io form within a widget._\
  _The form is prefilled with case data._
* **Table**\
  &#xNAN;_&#x50;resent array case data in a table within a widget._
* **Collection**\
  &#xNAN;_&#x50;resent array case data in a collection of cards within a widget._

<figure><img src="../../../.gitbook/assets/image (21).png" alt=""><figcaption><p>Choosing widget type</p></figcaption></figure>
{% endstep %}

{% step %}
### Choose widget width

The widget can be configured to display on any number of columns between 1 and 4.

<figure><img src="../../../.gitbook/assets/image (22).png" alt=""><figcaption><p>Choosing widget width</p></figcaption></figure>
{% endstep %}

{% step %}
### Choose widget style

A widget can either have a "Default" color scheme or it can be "High Contrast" to attract focus to that widget and it's content.

<figure><img src="../../../.gitbook/assets/image (23).png" alt=""><figcaption><p>Choosing widget style</p></figcaption></figure>
{% endstep %}

{% step %}
### Choose widget content

Depending on the widget type, the content is filled in differently. Click a card to view the details for configuring that widget type.
{% endstep %}
{% endstepper %}

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><strong>Fields widget</strong></td><td><em>Set of text data fields with a label and a value combined in a widget.</em></td><td></td><td><a href="fields-widget.md">fields-widget.md</a></td></tr><tr><td><strong>Custom component widget</strong></td><td><em>For complex content.</em><br><em>Connects to custom Angular code in the codebase.</em></td><td></td><td><a href="custom-component-widget.md">custom-component-widget.md</a></td></tr><tr><td><strong>Form.io widget</strong></td><td><em>A prefilled Form.io form that is presented in a widget.</em></td><td></td><td><a href="form.io-widget.md">form.io-widget.md</a></td></tr><tr><td><strong>Table widget</strong></td><td><em>Present case data from arrays in a table within a widget.</em> </td><td></td><td><a href="table-widget.md">table-widget.md</a></td></tr><tr><td><strong>Collection widget</strong></td><td><em>Present case data from arrays in a collection of cards within a widget.</em></td><td></td><td><a href="collection-widget.md">collection-widget.md</a></td></tr></tbody></table>

## JSON Editor

Widgets for a case can also be configured directly through a JSON editor. For process engineers, configuring widgets in JSON may offer greater control and efficiency. In the second tab of the Widget configuration UI, a JSON editor displays the complete widget configuration in JSON format. This editor includes error-checking functionality to ensure the JSON structure is correct.

<figure><img src="../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>
