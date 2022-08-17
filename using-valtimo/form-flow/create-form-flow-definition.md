# Creating a form flow definition

A form flow definition is a JSON document that defines steps and which steps can be reached
under what conditions when the current step is completed. Each step can have zero or more actions
(e.g. retrieve external data) that trigger when the task is opened or completed. Depending
on the type of step the step can be handled in a different way. The way a form is handled can
differ from a payment.

For information on how to link a form flow definition to a task, see 
[here](../form-link/configure-task.md).

## Definitions

To create form flow definition, the following steps are necessary:

* Create a form flow `.json` file under the following path: `*/resources/config/form-flow/`.

* Add each individual step to the form flow definition, e.g.:

    ```json
    {
        "startStep": "start",
        "steps": [
            {
                "key": "start"
            },
            {
                "key": "step2"
            },
            {
                "key": "step3"
            },
            {
                "key": "end"
            }
        ]
    }
    ```

* Add the next steps for each of the individual steps. This can be done through the `nextStep` property, which
supports a single step, or `nextSteps`, which supports multiple next steps. Each step should correspond to the key
of another step defined in this form flow. Since expressions are not yet supported for `nextSteps`, the first step
will always be selected. So in this example, step 2 will always be followed by step 3.

    ```json
    {
        "startStep": "start",
        "steps": [
            {
                "key": "start",
                "nextStep": "step2"
            },
            {
                "key": "step2",
                "nextSteps": [
                    {
                        "step": "step3"
                    },
                    {
                        "step": "end"
                    }
               ]
            },
            {
                "key": "step3",
                "nextStep": "end"
            },
            {
                "key": "end"
            }
        ]
    }
    ```

* Configure the step type. Currently, the only step type supported is `form`, which requires a `definition` property to
be set. This refers to the key of the form.

    ```json
    {
        "startStep": "start",
        "steps": [
            {
                "key": "start",
                "type": {
                    "name": "form",
                    "properties":  {
                        "definition": "start-form"
                    }
                },
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
                "nextSteps": [
                    {
                        "step": "step3"
                    },
                    {
                        "step": "end"
                    }
               ]
            },
            {
                "key": "step3",
                "type": {
                    "name": "form",
                    "properties":  {
                        "definition": "step3-form"
                    }
                },
                "nextStep": "end"
            },
            {
                "key": "end",
                "type": {
                    "name": "form",
                    "properties":  {
                        "definition": "end-form"
                    }
                }
            }
        ]
    }
    ```

* Add triggers to steps where necessary (e.g. to store data externally)



## Expressions

Form flow supports Spring Expression Language (SpEL) expressions in order to allow for more
complex actions when a step is opened or completed. Expressions can be recognized by the surrounding
`${ }` characters. The following additional properties are supported for steps:

* `onOpen`. Triggers the expressions when the step is opened, e.g. to retrieve external data.

* `onComplete`. Triggers the expressions when the step is complete, e.g. to store the results in a 
document.

Each of these properties supports more than one expression, e.g. when a step is opened, external data
from more than one source is retrieved.

```json
{
    "startStep": "start",
    "steps": [
        {
            "key": "start",
            "type": {
                "name": "form",
                "properties":  {
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
            "nextSteps": [
                {
                    "step": "step3"
                },
                {
                    "step": "end"
                }
           ]
        },
        {
            "key": "step3",
            "type": {
                "name": "form",
                "properties":  {
                    "definition": "step3-form"
                }
            },
            "nextStep": "end"
        },
        {
            "key": "end",
            "type": {
                "name": "form",
                "properties":  {
                    "definition": "end-form"
                }
            },
            "onComplete": ["${someDocumentService.saveFormFlowResult(additionalProperties, step.submissionData)}"]
        }
    ]
}
```

By default, SpEL allows access to every Spring bean from inside expressions. For security reasons
this has been changed to a whitelist instead, more information on how to whitelist Spring beans is
available [here](/extending-valtimo/form-flow/whitelist-spring-bean.md), and more information on SpEL
can be found [here](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#expressions).
