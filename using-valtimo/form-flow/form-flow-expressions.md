# Form flow expressions

Form flow supports Spring Expression Language (SpEL) expressions to allow for more
complex actions when a step is opened or completed. Expressions can be recognized by the surrounding
`${ }` characters. The following additional properties are supported for steps:

* `onBack`. Triggers the expressions when navigating to the previous step, e.g. to remove data from a document.

* `onOpen`. Triggers the expressions when the step is opened, e.g. to retrieve external data.

* `onComplete`. Triggers the expressions when the step is complete, e.g. to store the results in a 
document.

Each of these properties supports more than one expression, e.g. when a step is opened, external data
from more than one source is retrieved. These expressions are evaluated in order.

## SpEL bean whitelisting
SpEL by default can call any kind of bean to offer extra functionality to expressions. You can for instance call a
service to send an email, create a document based on a template etcetera. This is a powerful feature, but you can't
control what kind of beans might be called. Together with the possibility to use / fill expressions based user input,
and we have a major security concern.

Therefore, Valtimo has introduced an extra check surrounding the execution of SpEL expressions, only beans (i.e. classes
and services) that are whitelisted by either the Valtimo product team or a Valtimo implementation team are allowed to be
called by SpEL. This whitelisting is based on an annotation done in code and can not be altered or overridden by a
property.

If for example an evaluation calls a service, but that service is not whitelisted, SpEL will not be called to evaluate
and parse the expression. Valtimo will filter out any expressions that could be a security risk.

Non-bean calls are still allowed. You can for example just use a string or a math equation within SpEL as well, these do
not require a whitelisting. Examples of what you can enter as an expression in SpEL can be found in the spring
documentation (https://spring.getdocs.org/en-US/spring-framework-docs/docs/spring-core/expressions/expressions-language-ref.html).

All expression on this page are displayed in code within the function .parseExpression(). Anything you find within this
function can be set in the form flow definition with ${ }.
So for example if you read parseExpression("1 + 1") then in the form flow definition you would enter ${1 + 1}.

### Form flow SPeL beans

Form flow offers a single bean out of the box. The `ValtimoFormFlow bean`. This bean has several methods that can be
used inside a SPeL expression:

The method below completes a Camunda user task.
```spel
${valtimoFormFlow.completeTask(additionalProperties)}
```

The method below completes a Camunda user task _and_ saves the submission data into a default location in the json
document.

```spel
${valtimoFormFlow.completeTask(additionalProperties, step.submissionData)}
```

The method below completes a Camunda user task and saves the submission data into a location of your choosing. The third
parameter decides where the submission data should be saved. The third parameter expects a map from which the key
defines the location where the data should be saved, and the value is a location inside the `step.submissionData`.

```spel
${valtimoFormFlow.completeTask(additionalProperties, step.submissionData, {'doc:/address/streetName':'/street', 'pv:approved':'/approval'})}
```

## Form flow SpEL variables

Valtimo provides access to certain variables in the SpEL context:

- `step` This is an object containing information about the current step.
- `step.id` This is the id of the current form-flow-step-instance.
- `step.key` This is the key of the current form-flow-step-definition.
- `step.submissionData` This is a json object containing all data that was submitted during the completion of the step.
- `additionalProperties` This is an object containing some additional information that is known about the current step.
- `additionalProperties.processInstanceId` This is the id of the Camunda process instance.
- `additionalProperties.processInstanceBusinessKey` This is the business of the Camunda process instance
- `additionalProperties.taskInstanceId` This is the id of the Camunda user task.


## Example
A form flow example with SpEL expressions:

```json
{
    "startStep": "start",
    "steps": [
        {
            "key": "start",
            "type": {
                "name": "form",
                "properties": {
                    "definition": "start-form"
                }
            },
            "onOpen": ["${someService.retrieveData(additionalProperties)}"],
            "nextStep": "step2"
        },
        {
            "key": "step2",
            "type": {
                "name": "form",
                "properties":  {
                    "definition": "step2-form"
                }
            },
            "onBack": ["${someService.removeData(additionalProperties)}"],
            "nextSteps": [
                {
                    "step": "end"
                }
           ]
        },
        {
            "key": "end",
            "type": {
                "name": "form",
                "properties":  {
                    "definition": "end-form"
                }
            },
            "onComplete": ["${valtimoFormFlow.completeTask(additionalProperties, step.submissionData)}"]
        }
    ]
}
```
