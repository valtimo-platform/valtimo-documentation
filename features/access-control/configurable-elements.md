# Configurable elements

This page provides an overview of the configurable elements within Access Control in Valtimo.

In Access Control, policies can be defined for specific elements to manage user access and permissions precisely. These policies can be tailored with conditions, allowing for detailed and customized access configurations.

Each configurable element offers a set of actions that can be adjusted to fit your access needs. While not all actions are available for every element, each element provides a relevant subset of actions that logically apply to its function, ensuring that your access settings are both efficient and meaningful.\


## Actions configurable with Access control

<table><thead><tr><th width="131">Action</th><th width="423">Function</th><th>Examples</th></tr></thead><tbody><tr><td><strong>Assign</strong></td><td>Gives permission to assign that element to someone</td><td>Case or Task</td></tr><tr><td><strong>Assignable</strong></td><td>Makes users selectable when the element is assigned</td><td>Case or Task</td></tr><tr><td><strong>Create</strong></td><td>Enables users to create that element</td><td>Case or Case note</td></tr><tr><td><strong>Claim</strong></td><td>Enables users to claim the element</td><td>Case or Task</td></tr><tr><td><strong>Delete</strong></td><td>Enables users to delete the element</td><td>Case or Case note</td></tr><tr><td><strong>Modify</strong></td><td>Enables users to modify the elements details</td><td>Case or Case note</td></tr><tr><td><strong>View</strong></td><td>Gives permission to view the elements details</td><td>Case or Task</td></tr><tr><td><strong>View-list</strong></td><td>Gives permission to view the element in a list</td><td>Case, Task, Case note</td></tr></tbody></table>



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

Below the full list of elements within Valtimo that can and need to be configured in Access Control.\
Per element a list of configurable actions is documented and an example of the configuration is added. \
The available actions per element define what can be configured for that element.

### **Case Tab**

Configure access to view custom Case Tabs.

```json
{
    "resourceType": "com.ritense.case.domain.CaseTab",
    "action": "view",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"view"_

### **Case Note**

Configure access to view custom Case Notes.

```json
{
    "resourceType": "com.ritense.note.domain.Note",
    "action": "view",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"create", "delete, "modify",  "view-list"_



### **Case Document**

Configure access to the JSON document that is created for each Case.

```json
{
    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
    "action": "view",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"assign", "assignable", "create", "claim", "delete, "modify",  "view", "view-list"_



### **Case Document Snapshot**

Configure access to the JSON document snapshots that are created for a Case.

```json
{
    "resourceType": "com.ritense.document.domain.impl.snapshot.JsonSchemaDocumentSnapshot",
    "action": "view",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"view", "view-list"_



### Case Document Definition

Configure access to the document definition (JSON Schema) of a Case.

```json
{
    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocumentDefinition",
    "action": "view",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"assign", "assignable", "create", "claim", "delete, "modify", "view", "view-list"_



### Case Search Fields

Configure access to the configured search fields for a Case.

```json
{
    "resourceType": "com.ritense.document.domain.impl.searchfield.SearchField",
    "action": "view_list",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"view-list"_



### Process Execution&#x20;

Configure access to be able to start and execute processes.

```json
{
    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaExecution",
    "action": "create",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"create"_



### Process Tasks&#x20;

Configure access to be able to work with process user tasks.

```json
{
    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
    "action": "create",
    "conditions": []
}
```

**Configurable actions:**\
&#xNAN;_"assign", "assignable", "create", "claim", "view", "view-list"_

