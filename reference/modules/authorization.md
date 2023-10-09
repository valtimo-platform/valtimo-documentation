# Authorization

## Available resources
The access to the following resources is limited by Valtimo access control.

| Resource name                                   | Class name                                                             | Module   |
|-------------------------------------------------|:-----------------------------------------------------------------------|:---------|
| **[Document](#document)**                       | `com.ritense.document.domain.impl.JsonSchemaDocument`                  | Document |
| **[Document definition](#document-definition)** | `com.ritense.document.domain.impl.JsonSchemaDocumentDefinition`        | Document |
| **[Document snapshot](#document-snapshot)**     | `com.ritense.document.domain.impl.snapshot.JsonSchemaDocumentSnapshot` | Document |
| **[Search field](#search-field)**               | `com.ritense.document.domain.impl.searchfield.SearchField`             | Document |
| **[Note](#note)**                               | `com.ritense.note.domain.Note`                                         | Notes    |
| **[Task](#task)**                               | `com.ritense.valtimo.camunda.domain.CamundaTask`                       | Core     |
| **[Task identity link](#task)**                 | `com.ritense.valtimo.camunda.domain.CamundaIdentityLink`               | Core     |


### Document

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

No relations are supported for this type.

### Document definition

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

#### Supported actions

| Action         | key           | Description                                         |
|----------------|:--------------|:----------------------------------------------------|
| **View**       | `view`        | Allows reading of document snapshots and their data |
| **View list**  | `view_list`   | Allows retrieving lists of document snapshots       |

#### Supported relations

No relations are supported for this type

### Search field

#### Supported actions

| Action        | key         | Description                                               |
|---------------|:------------|:----------------------------------------------------------|
| **View list** | `view_list` | Allows use of search fields when searching for documents. |


#### Supported relations

No relations are supported for this type.

### Note

#### Supported actions

| Action         | key         | Description                       |
|----------------|:------------|:----------------------------------|
| **View list**  | `view_list` | Allows retrieving lists of notes. |
| **Create**     | `create`    | Allows creation of notes.         |
| **Modify**     | `modify`    | Allows modification of notes.     |
| **Delete**     | `delete`    | Allows deletion of notes.         |

#### Supported relations

| Related resource |
|------------------|
| **Document**     |

### Task

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

| Related resource |
|------------------|
| **Document**     |

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

| Operator   | Description                                      |
|:-----------|:-------------------------------------------------|
| `==`       | Equal to.                                        |
| `!=`       | Not equal to.                                    |
| `>`        | Greater than.                                    |
| `>=`       | Greater than or equal to.                        |
| `<`        | Smaller than.                                    |
| `<=`       | Smaller than or equal to.                        |
| `contains` | Checks if a collection contains the given value. |

### Expression

| key        | Description                                       | Examples                    |
|:-----------|:--------------------------------------------------|:----------------------------|
| `type`     | The type of condition. In this case `expression`. | `expression`                |
| `field`    | The field used to start the path from.            | `content.content`           |
| `path`     | The path that points to the field to compare to.  | `$.height`                  |
| `operator` | The operator for the comparison.                  | `==`, `<`                   |
| `value`    | The value to compare the field against.           | `20000`, `${currentUserId}` |
| `clazz`    | The name of the class that is found at the path.  | `int`                       |

#### Operators

| Operator   | Description                                      |
|:-----------|:-------------------------------------------------|
| `==`       | Equal to.                                        |
| `!=`       | Not equal to.                                    |
| `>`        | Greater than.                                    |
| `>=`       | Greater than or equal to.                        |
| `<`        | Smaller than.                                    |
| `<=`       | Smaller than or equal to.                        |
| `contains` | Checks if a collection contains the given value. |

### Container

| key            | Description                                                      | Examples                                               |
|:---------------|:-----------------------------------------------------------------|:-------------------------------------------------------|
| `type`         | The type of condition. In this case `container`.                 | `container`                                            |
| `resourceType` | The related resource type the conditions should apply to.        | `com.ritense.document.domain.impl.JsonSchemaDocument ` |
| `conditions`   | The conditions that should apply to the specified resource type. | See [supported conditions](#supported-conditions).     |
