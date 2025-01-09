# Configuring conditions

{% hint style="info" %}
This page requires:

* Knowledge of [JSON](https://www.json.org/)
{% endhint %}

\
Conditions can be used to further specify the policy on an element in Valtimo. When a condition is used in the policy it will match the conditions against the element it is trying to access. If the element matches the conditions it will be loaded, if a condition fails it will not be loaded.

Best explained with below use case:\
\
**Use case:**\
An implementation has 5 case types. 2 of those 5 case types should only be accessible to managers.\
\
**Solution:**

* Give the managers `ROLE_MANAGER`.
* Configure with conditions in PBAC that only `ROLE_MANAGER` can view these cases based on there Case Definition Name.
* Users without `ROLE_MANAGER` will no longer be able to view the 2 cases in Valtimo.

Below a number of examples of applying conditions in Access control policies.

### Expression permission with contains operator

In the example below, the `list_contains` operator is used to check if a specific flower is present inside the JsonSchemaDocument. Where the JsonSchemaDocument content could look like this: `{"flowers": ["lily", "rose", "daisy"]}`.

If the flower 'rose' is present in the JsonSchemaDocument, any user with the role `ROLE_USER` will be able to view that document.

```json
[
  {
    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
    "action": "view_list",
    "roleKey": "ROLE_USER",
    "conditions": [
      {
        "type": "expression",
        "field": "content.content",
        "path": "$.flowers",
        "operator": "list_contains",
        "value": "rose",
        "clazz": "java.util.Collection"
      }
    ]
  }
]
```

### Create case permissions

The following example demonstrates how to allow any user with `ROLE_USER` to create a case of type `leningen`. When trying to create a case, the case itself does not yet exist. So in order for conditions to be evaluated, they have to be defined based on the relation between the two resources,`JsonSchemaDocument` and `JsonSchemaDocumentDefinition`.

```json
[
  {
    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
    "action": "create",
    "roleKey": "ROLE_USER",
    "conditions": [
      {
        "type": "container",
        "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocumentDefinition",
        "conditions": [
          {
            "type": "field",
            "field": "id.name",
            "operator": "==",
            "value": "leningen"
          }
        ]
      }
    ]
  }
]
```

### Create process instance permissions

The example below shows how to allow users with `ROLE_USER` to create a process instance of process definition type `GenericProces`. When trying to create a process instance, the execution itself does not yet exist. So in order for conditions to be evaluated, they have to be defined based on the relation between the two resources, `CamundaExecution` and `CamundaProcessDefinition`.

```json
[
  {
    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaExecution",
    "action": "create",
    "roleKey": "ROLE_USER",
    "conditions": [
      {
        "type": "container",
        "resourceType": "com.ritense.valtimo.camunda.domain.CamundaProcessDefinition",
        "conditions": [
          {
            "type": "field",
            "field": "key",
            "operator": "==",
            "value": "GeneriekProces"
          }
        ]
      }
    ]
  }
]
```

### User task candidate groups permissions

Access to a user task is usually controlled by setting the 'Candidate groups' to a role. To make sure that the user task candidate groups work together with PBAC, an additional permission should be set. The example below shows how that can be done.

```json
[
  {
    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
    "action": "view_list",
    "roleKey": "ROLE_USER",
    "conditions": [
      {
        "type": "container",
        "resourceType": "com.ritense.valtimo.camunda.domain.CamundaIdentityLink",
        "conditions": [
          {
            "type": "field",
            "field": "groupId",
            "operator": "==",
            "value": "ROLE_USER"
          }
        ]
      }
    ]
  }
]
```

### User task document property permissions

Access to a user task can be controlled based on properties inside the JsonSchemaDocument. The example below shows how that can be done.

```json
[
  {
    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
    "action": "view_list",
    "roleKey": "ROLE_USER",
    "conditions": [
      {
        "type": "container",
        "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
        "conditions": [
          {
            "type": "expression",
            "field": "content.content",
            "path": "$.city",
            "operator": "==",
            "value": "Amsterdam",
            "clazz": "java.lang.String"
          }
        ]
      }
    ]
  }
]
```

### Document content value is present in an array of values

```json
{
  "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
  "action": "view",
  "conditions": [
    {
      "type": "expression",
      "field": "content.content",
      "path": "$.city",
      "operator": "in",
      "value": ["Amsterdam", "Utrecht"],
      "clazz": "java.lang.String"
    }
  ]
}
```

### The candidate group of a task is in the list of user roles

```json
{
  "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
  "action": "view",
  "conditions": [
    {
      "type": "container",
      "resourceType": "com.ritense.valtimo.camunda.domain.CamundaIdentityLink",
      "conditions": [
        {
          "type": "field",
          "field": "groupId",
          "operator": "in",
          "value": "${currentUserRoles}"
        }
      ]
    }
  ]
}
```

### Document content list value contains a specific value

```json
{
  "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
  "action": "view",
  "conditions": [
    {
      "type": "expression",
      "field": "content.content",
      "path": "$.cities",
      "operator": "list_contains",
      "value": "Amsterdam",
      "clazz": "java.lang.String"
    }
  ]
}
```
