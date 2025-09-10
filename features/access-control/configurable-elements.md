# Configurable elements

This page provides an overview of the configurable elements within Access Control in Valtimo.

In Access Control, policies can be defined for specific elements to manage user access and permissions precisely. These policies can be tailored with conditions, allowing for detailed and customized access configurations.

Each configurable element offers a set of actions that can be adjusted to fit your access needs. While not all actions are available for every element, each element provides a relevant subset of actions that logically apply to its function, ensuring that your access settings are both efficient and meaningful.

## Actions configurable with Access control

<table><thead><tr><th width="131" valign="top">Action</th><th width="423" valign="top">Function</th><th valign="top">Examples</th></tr></thead><tbody><tr><td valign="top"><strong>Assign</strong></td><td valign="top">Gives permission to assign that element to someone</td><td valign="top">Case or Task</td></tr><tr><td valign="top"><strong>Assignable</strong></td><td valign="top">Makes users selectable when the element is assigned</td><td valign="top">Case or Task</td></tr><tr><td valign="top"><strong>Create</strong></td><td valign="top">Enables users to create that element</td><td valign="top">Case or Case note</td></tr><tr><td valign="top"><strong>Claim</strong></td><td valign="top">Enables users to claim the element</td><td valign="top">Case or Task</td></tr><tr><td valign="top"><strong>Delete</strong></td><td valign="top">Enables users to delete the element</td><td valign="top">Case or Case note</td></tr><tr><td valign="top"><strong>Modify</strong></td><td valign="top">Enables users to modify the elements details</td><td valign="top">Case or Case note</td></tr><tr><td valign="top"><strong>View</strong></td><td valign="top">Gives permission to view the elements details</td><td valign="top">Case or Task</td></tr><tr><td valign="top"><strong>View-list</strong></td><td valign="top">Gives permission to view the element in a list</td><td valign="top">Case, Task, Case note</td></tr></tbody></table>

{% hint style="info" %}
Please note that it is not possible to nest actions in a configuration.\
For each separate action a configuration needs to be added to Access Control for that specific action.

<mark style="color:red;">Incorrect configuration:</mark>

```json
{
    "resourceType": "com.ritense.case.domain.CaseTab",
    "action": "view, create, modify",
    "conditions": []
}
```

<mark style="color:green;">Correct configuration:</mark>

```json
{
    "resourceType": "com.ritense.case.domain.CaseTab",
    "action": "view",
    "conditions": []
},
{
    "resourceType": "com.ritense.case.domain.CaseTab",
    "action": "create",
    "conditions": []
},
{
    "resourceType": "com.ritense.case.domain.CaseTab",
    "action": "modify",
    "conditions": []
}
```
{% endhint %}

## Elements configurable with Access control

Below the full list of elements within Valtimo that can and need to be configured in Access Control. Per element a list of configurable actions is documented and an example of the configuration is added. The available actions per element define what can be configured for that element.

* Cases
  * [Document](../case/document-definition.md#access-control)
  * [Document definition](../case/document-definition.md#access-control)
  * [Notes](../case/notes.md#access-control)
  * [Search fields](../case/search-fields.md#access-control)
  * [Tabs](../case/tabs/#access-control)
  * [Widgets](../case/tabs/widgets.md#access-control)
* [Dashboard](../dashboard/#access-control)
* Process
  * [Execution](../process/#access-control)
  * [Definition](../process/#access-control)
* Task
  * [Tasks](../tasks.md#access-control)
  * [Identity links](../tasks.md#access-control)
