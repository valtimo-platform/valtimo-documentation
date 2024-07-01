# Form view model

The Form View Model offers an alternative approach to handling forms for starting a process and user tasks, especially
useful for complex forms typically found in large custom projects. This module provides control over pre-filling,
onchange updates, and submissions.

Submission handling covers 2 scenarios:

- When a form is submitted for a `user task`
> **NOTE**: Developers should complete the task and modify the case in the handler.
- When a form is submitted for a `start form`
> **NOTE** Developers should start the process and create the case in the handler.

> This module does not create or update cases. Developers are responsible for managing case creation and updates themselves. It is recommended to use commands for this purpose. In short, any form of persistence is the responsibility of the developer.
>
> To support the developer in this process **default** command/handlers are provided.
> ``` kotlin
> val startProcessCommand = StartProcessCommand(
>     caseInstanceId = document.id().id,
>     processDefinitionKey = "myProcessDefinitionKey",
>     businessKey = "myBusinessKey"
> )
> dispatchCommand(startProcessCommand)
> 
> val completeTaskCommand = CompleteTaskCommand(taskId = task.id())
> 
> dispatchCommand(completeTaskCommand)
> ```

This step-by-step guide will explain the module and demonstrate its implementation.

- Step 1: Enabling the module in your project (see [Enabling the module](enabling-the-module.md))

- Step 2: Define the view-model structure for your form (see [Defining the view-model](defining-the-view-model.md))

- Step 3: Define the submission structure for your form (
  see [Defining the submission structure](defining-the-submission-structure.md))

- Step 4: Command handling (see [Command handling](../command-handling/command-handling.md))

- Step 5: Error handling (see [Error handling](error-handling.md))
