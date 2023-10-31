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

### Custom component

The `custom-component` step type is used to associate a step with a custom-made front-end component. The following properties are supported:

```json
    ...
      "type": {
        "name": "custom-component",
        "properties": {
          "componentId": "String" //The key of the component in the front-end
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
| `step`                 | `submissionData` | `JsonNode`               | The data submitted so far as a JsonNode.                        |
| `instance`             | `id`             | `FormFlowInstanceId`     | The ID of the form flow instance.                               |
| `additionalProperties` | -                | `Map<String, Any>`       | Additional properties stored as part of the form flow instance. |

## SpEL bean whitelisting
SpEL by default can call any kind of bean to offer extra functionality to expressions. You can for instance call a
service to send an email, create a document based on a template etcetera. This is a powerful feature, but you can't
control what kind of beans might be called. Together with the possibility to use / fill expressions based user input,
there is a major security concern.

Therefore, Valtimo has introduced an extra check surrounding the execution of SpEL expressions, only beans (i.e. classes
and services) that are whitelisted by either the Valtimo product team or a Valtimo implementation team are allowed to be
called by SpEL. This whitelisting is based on an annotation done in code and can not be altered or overridden by a
property.

If for example an evaluation calls a service, but that service is not whitelisted, SpEL will not be called to evaluate
and parse the expression. Valtimo will filter out any expressions that could be a security risk.

Non-bean calls are still allowed. You can for example just use a string or a math equation within SpEL as well, these do
not require a whitelisting. Examples of what you can enter as an expression in SpEL can be found in the spring
documentation (https://spring.getdocs.org/en-US/spring-framework-docs/docs/spring-core/expressions/expressions-language-ref.html).

All expressions passed as an argument to `parseExpression(...)` on this page can also be set in the form flow definition between `${}`
So for example if you read parseExpression("1 + 1") then in the form flow definition you would enter ${1 + 1}.

### Form flow SpEL beans

Form flow offers a single bean out of the box. The `ValtimoFormFlow bean`. This bean has several methods that can be
used inside a SPeL expression.

#### Completing a Camunda user task

The method below completes a Camunda user task. If there is submission data available, it will _not_ be saved.
```spel
${valtimoFormFlow.completeTask(additionalProperties)}
```

The method below completes a Camunda user task _and_ saves the submission data into a default location in the json
document.

#### Completing a Camunda user task and saving submission data

```spel
${valtimoFormFlow.completeTask(additionalProperties, step.submissionData)}
```

For example, if the submission data is:
```json
{
  "street": "Funenpark",
  "approved": true
}
```

The document JSON will get an extra `submission` field with all data from the `submissionData`. It will
override `submission` data if it already existed in the document JSON:
```json
{
  "submission": {
    "street": "Funenpark",
    "approved": true
  }
}
```

#### Completing a Camunda user task and saving submission data to defined location

The method below completes a Camunda user task and saves the submission data into a location of your choosing. The third
parameter decides where the submission data should be saved. The third parameter expects a map from which the key
defines the location where the data should be saved, and the value is a location inside the `step.submissionData`.

```spel
${valtimoFormFlow.completeTask(additionalProperties, step.submissionData, {'doc:/address/streetName':'/street', 'pv:approved':'/approval'})}
```

For example, if the submission data is:
```json
{
  "street": "Funenpark",
  "approved": true,
  "irrelevantProperty": 1234
}
```

The data will be added to the document JSON. If data was already present in the document JSON, it will be overwritten.
If the submission path is referencing to an object or array in the submission, the entire object/array is copied to the
document JSON.
```json
{
  "address": {
    "streetName": "Funenpark"
  }
}
```
The Camunda process will get an extra variable:
```json
{
  "approved": true
}
```

#### Starting a new case and saving submission data to defined location

The method below creates a new case and saves the submission data to the document and process variables. Storing data 
in other location is currently not supported. The second parameter decides where in the document the submission data 
should be saved. The second parameter expects a map from which the key defines the location where the data should be 
saved, and the value is a location inside the `step.submissionData`.

```spel
${valtimoFormFlow.startCase(instance.id, {'doc:/address/streetName':'/street', 'pv:approved':'/approval'})}
```

For example, if the submission data is:
```json
{
  "street": "Funenpark",
  "approved": true,
  "irrelevantProperty": 1234
}
```
A new document is created with this data. If the submission path is referencing to an object or array in the submission, 
the entire object/array is copied to the document JSON.

```json
{
  "address": {
    "streetName": "Funenpark"
  }
}
```
The Camunda process will be started with a process variable:
```json
{
  "approved": true
}
```

#### Starting a supporting process for a case

The method below start a new process instance for an existing case and saves the submission data to the document and 
process variables. Storing data in other location is currently not supported. The second parameter decides where in the 
document the submission data should be saved. The second parameter expects a map from which the key defines the location 
where the data should be saved, and the value is a location inside the `step.submissionData`.

```spel
${valtimoFormFlow.startSupportingProcess(instance.id, {'doc:/address/streetName':'/street', 'pv:approved':'/approval'})}
```

For example, if the submission data is:
```json
{
  "street": "Funenpark",
  "approved": true,
  "irrelevantProperty": 1234
}
```

The data will be added to the document JSON. If data was already present in the document JSON, it will be overwritten.
If the submission path is referencing to an object or array in the submission, the entire object/array is copied to the
document JSON.

```json
{
  "address": {
    "streetName": "Funenpark"
  }
}
```
The Camunda process will be started with a process variable:
```json
{
  "approved": true
}
```
