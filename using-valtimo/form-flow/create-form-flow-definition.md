# Creating a form flow definition

A form flow definition is a JSON document that defines steps and which steps can be reached
under what conditions when the current step is completed. Each step can have zero or more actions
(e.g. retrieve external data) that trigger when the task is opened or completed. Depending
on the type of step, the step can be handled in a different way. The way a form is handled can
differ from a payment, for example.

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
be set. This refers to the key of the form. For more information on step types, see [here](/reference/modules/form-flow.md#step-types)

  Which properties are required to be set depends on the step type.

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

* Add triggers to steps where necessary (e.g. to store data externally). See below for more information.

## Expressions

Form flow supports Spring Expression Language (SpEL) expressions to allow for more
complex actions when a step is opened or completed. More information can be
found [here](/form-flow-expressions.md)
