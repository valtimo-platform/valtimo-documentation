
# 13.3.0



{% hint style="info" %}
**Release date 08-10-2025**
{% endhint %}

## New Features

* **Add Case Objects to Case** &#x20;

A new plugin action has been added to the Zaken API Plugin, allowing users to create a case object directly within a process. This feature can be used whenever someone needs to link an existing  object to a case.

* **Enhanced “Create Case” Plugin Action**&#x20;

The “Create Case” plugin action has been improved to allow users to fill in more case details when creating a new case in Open Zaak. Previously, only the required fields were included when a case was created. With this update, additional (optional) fields can now be completed, making it easier to register cases with all the relevant information right from the start.

## Bugfixes

* Case widgets of type FormIO will now correctly finish loading and no longer cause the widget
  page to be stuck on a loading animation.
* The document files endpoint in the Documents tab is now called only once, improving performance and preventing duplicate requests when many documents are linked to a case.
* The task status shown in the case details is now fully visible, ensuring the status text is no longer partially cut off.
* The issue with getProcessDefinitionKey is fixed.
* Migration issue _with Request Plugin_ is resolved.

