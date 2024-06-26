# Defining the submission structure

The submission structure is composed of the raw submission, a contract and a submission handler.

## Raw submission
This is the submission data you get from submitting a FormIO form. It is a JSON object that contains the data from the form.

## Contract
The contract is a data class that defines the structure of the submission data. It is used to validate the raw submission data and to convert it to a submission object.

The contract should be a data class that implements the `Submission` interface.

You can re-use the view-model data class as the contract. The view-model data class should implement the `Submission` interface.

Here is an example of a contract:

```kotlin
data class TestSubmission(
    val firstName: String,
    val lastName: String,
    val fullName: String,
    val age: Int,
    val adultPermission: Boolean? = null
) : Submission
```

## Submission handlers

There are two types of submission handlers: `FormViewModelStartSubmissionHandler` and `FormViewModelUserTaskSubmissionHandler`.

Each submission handler is a interface that is used to handle the submission data. 

The `supports()` method is used to find the correct handler for the given form.

The `handle(...)` method is used to handle the submission data. 

> You can handle this data any way you want, but we highly recommend using commands (see [Command handling](../command-handling/command-handling.md)).

The submission handler also needs to be registered as a bean in the Spring context.

Here is an example implementation of a submission handler for a user task:

```kotlin
@Component
class TestSubmissionHandler : FormViewModelUserTaskSubmissionHandler<TestSubmission> {

    override fun supports(formName: String): Boolean {
        return formName == "test"
    }

    override fun <T> handle(submission: T, task: CamundaTask, businessKey: String) {
        submission as TestSubmission
        val exampleCommand = ExampleCommand(
            age = submission.age
        )
        dispatchCommand(exampleCommand)
    }
}
```

## Contract validation
On start-up a class will validate that the structure of the `Submission` matches the submission structure of the form. If not, an error message will be printed in the logs. Note that extra properties will be ignored in the submission and thus cannot be used.

Here is an example of the error message:
```
The following properties are missing in the user task submission for form (user-task-2): [age]
```

More info on the validation can be found here: [Contract validation on ViewModel and Submission](contract-validation.md)
