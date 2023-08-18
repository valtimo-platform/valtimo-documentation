# Authorization

## Available resources
The access to the following resources is limited by Valtimo access control.

| Resource name                                   | Class name                                                      | Module   |
|-------------------------------------------------|:----------------------------------------------------------------|:---------|
| **[Document](#document)**                       | `com.ritense.document.domain.impl.JsonSchemaDocument`           | Document |
| **[Document definition](#document-definition)** | `com.ritense.document.domain.impl.JsonSchemaDocumentDefinition` | Document |
| **[Document snapshot](#document-snapshot)**     | `com.ritense.document.domain.impl.JsonSchemaDocumentSnapshot`   | Document |
| **[Search field](#search-field)**               | `com.ritense.document.domain.impl.searchfield.SearchField`      | Document |
| **[Note](#note)**                               | `com.ritense.note.domain.Note`                                  | Notes    |
| **[Task](#task)**                               | `com.ritense.valtimo.camunda.domain.CamundaTask`                | Core     |


### Document

#### Supported actions

| Action         | key           | Description                                                               |
|----------------|:--------------|:--------------------------------------------------------------------------|
| **View**       | `view`        | Allows reading of documents and their data                                |
| **View list**  | `view_list`   | Allows retrieving lists of documents                                      |
| **Create**     | `create`      | Allows creation of documents                                              |
| **Modify**     | `modify`      | Allows modification of documents                                          |
| **Delete**     | `delete`      | Allows deletion of documents                                              |
| **Claim**      | `claim`       | Allows users to assign themselves as the case handler                     |
| **Assign**     | `assign`      | Allows assigning a case handler of both the current and other users       |
| **Assignable** | `assignable`  | Allows users with permissions on this action to be assigned to a document |


#### Supported relations

No relations are supported for this type

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

| Action        | key         | Description                                              |
|---------------|:------------|:---------------------------------------------------------|
| **View list** | `view_list` | Allows use of search fields when searching for documents |


#### Supported relations

No relations are supported for this type

### Note

#### Supported actions

| Action         | key         | Description                      |
|----------------|:------------|:---------------------------------|
| **View list**  | `view_list` | Allows retrieving lists of notes |
| **Create**     | `create`    | Allows creation of notes         |
| **Modify**     | `modify`    | Allows modification of notes     |
| **Delete**     | `delete`    | Allows deletion of notes         |

#### Supported relations

| Related resource |
|------------------|
| **Document**     |

### Task

#### Supported actions

| Action         | key          | Description                                                             |
|----------------|:-------------|:------------------------------------------------------------------------|
| **View**       | `view`       | Allows viewing tasks                                                    |
| **View list**  | `view_list`  | Allows retrieving lists of tasks                                        |
| **Claim**      | `claim`      | Allows users to assign themselves as the task                           |
| **Assign**     | `assign`     | Allows assigning a tasks handler of both the current and other users    |
| **Assignable** | `assignable` | Allows users with permissions on this action to be assigned to the task |
| **Complete**   | `complete`   | Allows users to complete the task                                       |

#### Supported relations

| Related resource |
|------------------|
| **Document**     |
