# Processes

Processes (BPMN 2.0) are used in Valtimo to gather case information needed for that specific case. At least one process needs to be linked to the case definition in order to be able to start new cases based on that case definition. Next to this a valid form needs to be linked to the "start event" of that process so that this form is displayed when the "Create New Case" button is clicked.

This case tab only focusses on linking the process to the case. A form does not have to be connected to the process in order to link the process to the case definition.

{% hint style="info" %}
This page requires:

* A process definition
{% endhint %}

## Linking a process to the case definition

Linking processes to the case definition can be done via the UI or the IDE.

{% tabs %}
{% tab title="Via UI" %}
<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption><p>Link a process</p></figcaption></figure>

The "Link process" button will open a modal with the option to select any process that exists within the implementation.



<div align="left" data-full-width="false">

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption><p>Link a process to a case definition</p></figcaption></figure>

</div>

The checkboxes can be used to identify what type of process is being linked. Some processes are relevant when a new case is started and other processes are only relevant in certain states of the case.\
&#x20;

* [x] **Process creates new case**

These types of processes generally have the start form configured that is used to create new cases. Connect the process and select the checkbox. At least one process should have this option selected, otherwise the "Create New Case" button will remain disabled.

Multiple start forms can exist for a single case and if this is configured a pre-selection modal will appear presenting available start forms when the "Create New Case**"** button is clicked.\
&#x20;

* [x] **Can be started within existing case**

Select this checkbox for processes that support a case during a specific period or state. These processes are available under the "Start" button on any tab of the case details.\
&#x20;

* [x] **Do not select anything**

Leave both checkboxes empty when a sub-process needs to be added to the case definition. In larger process models it's often helpful to move parts of the process to a sub process that can be activated via a so-called "Call activity" element in the main process.

These sub-processes are not starting processes for the case and should not appear in the Case actions menu under the Start button in the case details UI. It is important to link these sub-processes to the Case definition in order to automatically store the data that is fetched by these processes in the JSON document of that case.\
&#x20;
{% endtab %}

{% tab title="Via IDE" %}

{% endtab %}
{% endtabs %}

