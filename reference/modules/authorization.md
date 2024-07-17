# Authorization

## Available resources
The access to the following resources is limited by Valtimo access control.

| Resource name                                   | Resource type                                                          | Module   |
|-------------------------------------------------|:-----------------------------------------------------------------------|:---------|
| **[Document](#document)**                       | `com.ritense.document.domain.impl.JsonSchemaDocument`                  | Document |
| **[Document definition](#document-definition)** | `com.ritense.document.domain.impl.JsonSchemaDocumentDefinition`        | Document |
| **[Document snapshot](#document-snapshot)**     | `com.ritense.document.domain.impl.snapshot.JsonSchemaDocumentSnapshot` | Document |
| **[Search field](#search-field)**               | `com.ritense.document.domain.impl.searchfield.SearchField`             | Document |
| **[Note](#note)**                               | `com.ritense.note.domain.Note`                                         | Notes    |
| **[Execution](#execution)**                     | `com.ritense.valtimo.camunda.domain.CamundaExecution`                  | Core     |
| **[Process definition](#process-definition)**   | `com.ritense.valtimo.camunda.domain.CamundaProcessDefinition`          | Core     |
| **[Task](#task)**                               | `com.ritense.valtimo.camunda.domain.CamundaTask`                       | Core     |
| **[Task identity link](#task-identity-link)**   | `com.ritense.valtimo.camunda.domain.CamundaIdentityLink`               | Core     |
| **[Case tab](#case-tab)**                       | `com.ritense.case.domain.CaseTab`                                      | Case     |
| **[Case tab widget](#case-tab-widget)**         | `com.ritense.case_.domain.tab.CaseWidgetTabWidget`                     | Case     |

### Document
Resource type: `com.ritense.document.domain.impl.JsonSchemaDocument`

#### Supported actions
| Action         | key           | Description                                                                 |
|----------------|:--------------|:----------------------------------------------------------------------------|
| **View**       | `view`        | Allows reading of documents and their data.                                 |
| **View list**  | `view_list`   | Allows retrieving lists of documents.                                       |
| **Create**     | `create`      | Allows creation of documents.                                               |
| **Modify**     | `modify`      | Allows modification of documents.                                           |
| **Delete**     | `delete`      | Allows deletion of documents.                                               |
| **Claim**      | `claim`       | Allows users to assign themselves as the case handler.                      |
| **Assign**     | `assign`      | Allows assigning a case handler of both the current and other users.        |
| **Assignable** | `assignable`  | Allows users with permissions for this action to be assigned to a document. |

#### Supported relations
| Related resource                                |
|-------------------------------------------------|
| **[Document definition](#document-definition)** |

### Document definition
Resource type: `com.ritense.document.domain.impl.JsonSchemaDocumentDefinition`

#### Supported actions
| Action        | key         | Description                                     |
|---------------|:------------|:------------------------------------------------|
| **View**      | `view`      | Allows reading of documents definitions         |
| **View list** | `view_list` | Allows retrieving lists of document definitions |
| **Create**    | `create`    | Allows creation of document definitions         |
| **Modify**    | `modify`    | Allows modification of document definitions     |
| **Delete**    | `delete`    | Allows deletion of document definitions         |

#### Supported relations

No relations are supported for this type

### Document snapshot
Resource type: `com.ritense.document.domain.impl.snapshot.JsonSchemaDocumentSnapshot`
#### Supported actions
| Action         | key           | Description                                         |
|----------------|:--------------|:----------------------------------------------------|
| **View**       | `view`        | Allows reading of document snapshots and their data |
| **View list**  | `view_list`   | Allows retrieving lists of document snapshots       |

#### Supported relations
No relations are supported for this type

### Search field
Resource type: `com.ritense.document.domain.impl.searchfield.SearchField`

#### Supported actions
| Action        | key         | Description                                               |
|---------------|:------------|:----------------------------------------------------------|
| **View list** | `view_list` | Allows use of search fields when searching for documents. |

#### Supported relations
No relations are supported for this type.

### Note
Resource type: `com.ritense.note.domain.Note`

#### Supported actions
| Action         | key         | Description                       |
|----------------|:------------|:----------------------------------|
| **View list**  | `view_list` | Allows retrieving lists of notes. |
| **Create**     | `create`    | Allows creation of notes.         |
| **Modify**     | `modify`    | Allows modification of notes.     |
| **Delete**     | `delete`    | Allows deletion of notes.         |

#### Supported relations
| Related resource          |
|---------------------------|
| **[Document](#document)** |

### Execution
Resource type: `com.ritense.valtimo.camunda.domain.CamundaExecution`

#### Supported actions
| Action         | key          | Description                                                               |
|----------------|:-------------|:--------------------------------------------------------------------------|
| **Create**     | `create`     | Allows creating an execution.                                             |

#### Supported relations
| Related resource                              |
|-----------------------------------------------|
| **[Process definition](#process-definition)** |

### Process definition
Resource type: `com.ritense.valtimo.camunda.domain.CamundaProcessDefinition`

#### Supported actions
No actions are currently supported.

#### Supported relations
No relations are currently supported.

### Task
Resource type: `com.ritense.valtimo.camunda.domain.CamundaTask`

#### Supported actions
| Action         | key          | Description                                                              |
|----------------|:-------------|:-------------------------------------------------------------------------|
| **View**       | `view`       | Allows viewing tasks.                                                    |
| **View list**  | `view_list`  | Allows retrieving lists of tasks.                                        |
| **Claim**      | `claim`      | Allows users to assign themselves as the task                            |
| **Assign**     | `assign`     | Allows assigning a tasks handler of both the current and other users.    |
| **Assignable** | `assignable` | Allows users with permissions for this action to be assigned to the task. |
| **Complete**   | `complete`   | Allows users to complete the task.                                       |

#### Supported relations
| Related resource                              |
|-----------------------------------------------|
| **[Document](#document)**                     |
| **[Task identity link](#task-identity-link)** |

### Task identity link
Resource type: `com.ritense.valtimo.camunda.domain.CamundaIdentityLink`

#### Supported actions
No actions are supported for this type.

### Case tab
Resource type: `com.ritense.case.domain.CaseTab`

#### Supported actions
| Action         | key           | Description                    |
|----------------|:--------------|:-------------------------------|
| **View**       | `view`        | Allows viewing tabs of a case. |

#### Supported relations
| Related resource                                |
|-------------------------------------------------|
| **[Document definition](#document-definition)** |

### Case tab widget
Resource type: `com.ritense.case_.domain.tab.CaseWidgetTabWidget`

#### Supported actions
| Action         | key           | Description                           |
|----------------|:--------------|:--------------------------------------|
| **View**       | `view`        | Allows viewing widgets on a case tab. |

#### Supported relations
No relations are supported for this type.

## Supported conditions
The following conditions can be used with their respective structures:

| Resource name                 | Key          | Description                                                                                          |
|-------------------------------|:-------------|:-----------------------------------------------------------------------------------------------------|
| **[Field](#field)**           | `field`      | Allows conditions to be applied to specific fields.                                                  |
| **[Expression](#expression)** | `expression` | Allows JsonPath expressions to search through JSON.                                                  |
| **[Container](#container)**   | `container`  | Allows more complex conditions by denoting the related entity the nested conditions should apply to. |

### Field

| key        | Description                                     | Examples                                  |
|:-----------|:------------------------------------------------|:------------------------------------------|
| `type`     | The type of condition. In this case `field`.    | `field`                                   |
| `field`    | The field the value should be compared against. | `assigneeId`, `documentDefinitionId.name` |
| `operator` | The operator for the comparison.                | `==`, `<`                                 |
| `value`    | The value to compare the field against.         | `20000`, `${currentUserId}`               |

#### Operators

| Operator        | Description                                             |
|:----------------|:--------------------------------------------------------|
| `==`            | Equal to.                                               |
| `!=`            | Not equal to.                                           |
| `>`             | Greater than.                                           |
| `>=`            | Greater than or equal to.                               |
| `<`             | Smaller than.                                           |
| `<=`            | Smaller than or equal to.                               |
| `list_contains` | Checks if a collection contains the given value.        |
| `in`            | Checks if a value is contained in the given collection. |

### Expression

| key        | Description                                       | Examples                    |
|:-----------|:--------------------------------------------------|:----------------------------|
| `type`     | The type of condition. In this case `expression`. | `expression`                |
| `field`    | The field used to start the path from.            | `content.content`           |
| `path`     | The path that points to the field to compare to.  | `$.height`                  |
| `operator` | The operator for the comparison.                  | `==`, `<`                   |
| `value`    | The value to compare the field against.           | `20000`, `${currentUserId}` |
| `clazz`    | The name of the class that is found at the path.  | `java.lang.Integer`         |

#### Operators

| Operator        | Description                                             |
|:----------------|:--------------------------------------------------------|
| `==`            | Equal to.                                               |
| `!=`            | Not equal to.                                           |
| `>`             | Greater than.                                           |
| `>=`            | Greater than or equal to.                               |
| `<`             | Smaller than.                                           |
| `<=`            | Smaller than or equal to.                               |
| `list_contains` | Checks if a collection contains the given value.        |
| `in`            | Checks if a value is contained in the given collection. |

### Container

| key            | Description                                                      | Examples                                               |
|:---------------|:-----------------------------------------------------------------|:-------------------------------------------------------|
| `type`         | The type of condition. In this case `container`.                 | `container`                                            |
| `resourceType` | The related resource type the conditions should apply to.        | `com.ritense.document.domain.impl.JsonSchemaDocument ` |
| `conditions`   | The conditions that should apply to the specified resource type. | See [supported conditions](#supported-conditions).     |

### Special values for the value field
| Value                 | Description                                     |
|:----------------------|:------------------------------------------------|
| `${currentUserId}`    | The identifier assigned to the current user.    |
| `${currentUserEmail}` | The email address the current user has.         |
| `${currentUserRoles}` | The list of roles the current user has.         |
