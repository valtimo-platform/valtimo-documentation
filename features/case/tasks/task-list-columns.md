# Task list columns

Task list columns can be configured to change the visible columns in the task list.

## Available list columns

The following properties can be shown in the task list:

* Properties from the document, with the '`doc:`' prefix. E.g.: `doc:first-name`
* Properties from the task, with the '`task:`' prefix. The following properties are available:
  * `createTime`
  * `name`
  * `assignee`
  * `dueDate`

{% hint style="info" %}
Starting Valtimo `12.6.0`, the 'variable' property can be used in the task list. Using the variable property, process variables that exist in the process instance of the task can be shown. A variable property can be configured using the `task:variable.firstName` notation.
{% endhint %}

## Configuring task list columns

{% tabs %}
{% tab title="Via UI" %}
To be documented.
{% endtab %}

{% tab title="Via IDE" %}
#### Autodeployment

1. Task list columns can be autodeployed by adding json files on the classpath. These files should be created under the following path: `*/resources/config/case/{case-definition-key}/{version-tag}/case/task-list/` end with `.case-task-list.json` to be eligible for autodeployment.
2. Specify the columns that should be displayed for tasks for the case definition.

{% code title="my-case.case-task-list.json" %}
```json
[
  {
    "title": "First name",
    "key": "first-name",
    "path": "doc:first-name",
    "displayType": {
      "type": "text",
      "displayTypeParameters": {}
    },
    "sortable": false
  },
  {
    "title": "Last name",
    "key": "last-name",
    "path": "doc:last-name",
    "displayType": {
      "type": "text",
      "displayTypeParameters": {}
    },
    "sortable": true,
    "defaultSort": "ASC"
  }
]
```
{% endcode %}
{% endtab %}
{% endtabs %}
