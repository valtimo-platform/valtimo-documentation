# Form Flow

## Step types

The following step types are supported by form flow:

### Form

The `form` step type is used to associate a step with a specific form. The following properties are supported:

```json
    ...
      "type": {
        "name": "form",
        "properties": {
          "definition": "String" //The ID of the form
        }
      }
    ...
```

## Available properties in SpEL context

The following properties are available in a SpEL context:

| Property               | Sub Property     | Type                     | Description                                                     |
|------------------------|:-----------------|:-------------------------|:----------------------------------------------------------------|
| `step`                 | -                | `Map<String, Any>`       | Information regarding the current step, e.g. ID, key.           |
| `step`                 | `id`             | `FormFlowStepInstanceId` | The ID of the form flow step instance.                          |
| `step`                 | `key`            | `String`                 | The current step.                                               |
| `step`                 | `submissionData` | `String`                 | The data submitted so far as a json string.                     |
| `additionalProperties` | -                | `Map<String, Any>`       | Additional properties stored as part of the form flow instance. |



