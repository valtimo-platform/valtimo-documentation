# Processes

{% hint style="info" %}
This page requires:

* A [document definition](document.md)
* A process definition
{% endhint %}

## Linking a process to a case

Before a process can be started, it has to be linked to a case first. There are two ways to do this.

{% tabs %}
{% tab title="Via UI" %}
<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption><p>Link a process</p></figcaption></figure>

A modal will appear with the option to select any process within that Valtimo implementation.

<div align="left" data-full-width="false">

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption><p>Link a process to a case definition</p></figcaption></figure>

</div>

The checkboxes can be used to identify what type of process is being linked.\
Some processes are relevant for when a new case is started and other processes are only relevant in some states of the case.

* [x] **Process creates new case**

These types of processes generally have the start form configured that is used to create new cases. Connect the process and select the checkbox. At least 1 process should have this option selected, otherwise the Create case button will remain disabled for this case definition.

Multiple start forms can exist for a single case and if this is configured a pre-selection modal will appear presenting available start forms when the **Create New Case** button is clicked.

* [x] **Can be started within existing case**

Select this checkbox for processes that support a case during a specific period or state. These processes are available under the **Start** button on any tab of the case details.
{% endtab %}

{% tab title="Via IDE" %}

{% endtab %}
{% endtabs %}

