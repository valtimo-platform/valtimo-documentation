# Process beans

Process beans are Spring beans that can be used inside a Camunda BPMN process. The BPMN expression fields have access to
all process beans. This page gives an overview of all available process beans.

## CorrelationService

This process bean provides a way to manipulate jobs within the current process.

```kotlin
fun sendStartMessage(message: String, businessKey: String)
fun sendStartMessage(message: String, businessKey: String, variables: Map<String, Any>?)
fun sendStartMessageWithProcessDefinitionKey(message: String, targetProcessDefinitionKey: String, businessKey: String, variables: Map<String, Any>?)
fun sendCatchEventMessage(message: String, businessKey: String)
fun sendCatchEventMessage(message: String, businessKey: String, variables: Map<String, Any>?)
fun sendCatchEventMessageToAll(message: String, businessKey: String)
fun sendCatchEventMessageToAll(message: String, businessKey: String, variables: Map<String,Any>?)
```

Information on all methods can be found [here](../using-valtimo/process/process-beans/correlation-service.md).

## JobService

This process bean provides a way to manipulate jobs within the current process.

```kotlin
fun updateTimerDueDateByActivityId(dueDateString: String, activityId: String, execution: DelegateExecution)
fun addOffsetInMillisToTimerDueDateByActivityId(millisecondsToAdd: Long, activityId: String, execution: DelegateExecution)
```

Information on all methods can be found [here](../using-valtimo/process/process-beans/job-service.md).

## ProcessDocumentGenerator

This process bean provides an interface for generating documents.

```kotlin
fun generate(execution: DelegateExecution, mediaType: String, templateIdentifier: String)
```

- `generate` - provides an interface for generating documents. This method only works if your implementation has
  overriden the interface to actually generate a document.

## MailService

This process bean is for sending emails.

```kotlin
fun sendElementTemplateTaskMail(execution: DelegateExecution)
```

- `sendElementTemplateTaskMail` - is able to send an email using the configured Camunda extension properties. The extension properties are:
  - `mailSendTaskFrom` - The email-address of the sender.
  - `mailSendTaskSubject` - The subject of the email.
  - `mailSendTaskTo` - The email-address of the receiver.
  - `mailSendTaskTemplate` - The template that is used for the email. The template often has placeholders. The method
    uses all process variables as possible placeholders for the template.

## DocumentDelegate

This process bean is deprecated. Please use the `DocumentDelegateService` process bean instead.

## DocumentVariableDelegate

This process bean is deprecated. Please use the `DocumentDelegateService` process bean instead.

## DocumentDelegateService

This process bean is for retrieving and updating the document.

```kotlin
fun getDocumentVersion(execution: DelegateExecution)
fun getDocumentCreatedOn(execution: DelegateExecution)
fun getDocumentCreatedBy(execution: DelegateExecution)
fun getDocumentModifiedOn(execution: DelegateExecution)
fun getDocumentAssigneeId(execution: DelegateExecution)
fun getDocumentAssigneeFullName(execution: DelegateExecution)
fun getDocument(execution: DelegateExecution)
fun findValueByJsonPointer(jsonPointer: String?, execution: DelegateExecution?)
fun findValueByJsonPointerOrDefault(jsonPointer: String?, execution: DelegateExecution, defaultValue: Any)
fun setAssignee(execution: DelegateExecution, userEmail: String?)
fun unassign(execution: DelegateExecution)
```

- `getDocumentVersion` - Returns the version of the document.
- `getDocumentCreatedOn` - Returns the creation date of the document.
- `getDocumentCreatedBy` - Returns the email of the creator of the document.
- `getDocumentModifiedOn` - Returns the last modified date of the document.
- `getDocumentAssigneeId` - Returns the ID of the person assigned to the document version.
- `getDocumentAssigneeFullName` - Returns full name of the person assigned to the document.
- `getDocument` - Returns the entire document as an object.
- `findValueByJsonPointer` - Returns the value retrieved from the document at a given pointer.
- `findValueByJsonPointerOrDefault` - Returns the value retrieved from the document at a given pointer.
- `setAssignee` - Assigns a person to a document.
- `unassign` - Removes the assigned person from a document.

## ProcessDocumentsService

This process bean is for retrieving and updating the document.

```kotlin
fun startProcessByProcessDefinitionKey(processDefinitionKey: String, documentId: String)
fun startProcessByProcessDefinitionKey(processDefinitionKey: String, documentId: String, variables: Map<String, Any>?)
```

- `startProcessByProcessDefinitionKey` - Starts a new process and attaches it to the current document.
