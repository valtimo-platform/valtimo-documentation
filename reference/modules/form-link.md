# Form links (deprecated)

## Supported form types

| Form type                | Description                                                                                  | Module              |
|--------------------------|:---------------------------------------------------------------------------------------------|:--------------------|
| **Form definition**      | Connects the user task to a form definition included in the application.                     | `form`              |
| **Form flow definition** | Connects the user task or start event to a form flow definition included in the application. | `form-flow-valtimo` |
| **Internal route**       | Connects the user task or start event to a custom Angular form in the application.           | -                   |
| **External URL**         | Connects the user task or start event to an external web form.                               | -                   |

## Supported properties for configuring form links

| Property              | Description                                                   | Example                         | 
|:----------------------|:--------------------------------------------------------------|:--------------------------------|
| `formName`            | The identifier of the form.                                   | `start-form-personal-loan`      |
| `formFlowName`        | The identifier of the form flow.                              | `start-form-flow-personal-loan` |
| `formLinkElementId`   | The activity identifier for the activity the form links to.   | `start-personal-loan-event`     |
| `formAssociationType` | The camunda activity type for the activity the form links to. | `start-event`                   |

## Supported form association types

| Property      | Description           |
|:--------------|:----------------------|
| `start-event` | Start event activity. |
| `user-task`   | User task activity.   |
