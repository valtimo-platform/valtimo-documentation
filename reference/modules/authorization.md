# Authorization

## Available resources
The access to the following resources is limited by Valtimo access control.

| Resource name                     | Class name                                                 | Module   |
|-----------------------------------|:-----------------------------------------------------------|:---------|
| **[Document](#document)**         | `com.ritense.document.domain.impl.JsonSchemaDocument`      | Document |
| **[Search field](#search-field)** | `com.ritense.document.domain.impl.searchfield.SearchField` | Document |
| **[Note](#note)**                 | `com.ritense.note.domain.Note`                             | Notes    |
| **[Task](#task)**                 | `com.ritense.valtimo.camunda.domain.CamundaTask`           | Core     |


### Document

#### Supported actions

| Action         | key           | Description                                                                |
|----------------|:--------------|:---------------------------------------------------------------------------|
| **View**       | `view`        | Allows reading of documents and their data.                                |
| **View list**  | `view_list`   | Allows retrieving lists of documents.                                      |
| **Create**     | `create`      | Allows creation of documents.                                              |
| **Modify**     | `modify`      | Allows modification of documents.                                          |
| **Delete**     | `delete`      | Allows deletion of documents.                                              |
| **Claim**      | `claim`       | Allows users to assign themselves as the case handler.                     |
| **Assign**     | `assign`      | Allows assigning a case handler of both the current and other users.       |
| **Assignable** | `assignable`  | Allows users with permissions on this action to be assigned to a document. |


#### Supported relations

No relations are supported for this type.

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
| **Assignable** | `assignable` | Allows users with permissions on this action to be assigned to the task. |
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


### Expression

| key        | Description                                       | Examples                    |
|:-----------|:--------------------------------------------------|:----------------------------|
| `type`     | The type of condition. In this case `expression`. | `expression`                |
| `field`    | The field used to start the path from.            | `content.content`           |
| `path`     | The path that points to the field to compare to.  | `$.height`                  |
| `operator` | The operator for the comparison.                  | `==`, `<`                   |
| `value`    | The value to compare the field against.           | `20000`, `${currentUserId}` |
| `clazz`    | The name of the class that is found at the path.  | `int`                       |


### Container

| key            | Description                                                      | Examples                                               |
|:---------------|:-----------------------------------------------------------------|:-------------------------------------------------------|
| `type`         | The type of condition. In this case `container`.                 | `container`                                            |
| `resourceType` | The related resource type the conditions should apply to.        | `com.ritense.document.domain.impl.JsonSchemaDocument ` |
| `conditions`   | The conditions that should apply to the specified resource type. | See [supported conditions](#supported-conditions).     |
