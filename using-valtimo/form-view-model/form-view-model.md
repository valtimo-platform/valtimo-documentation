# Form view model

The Form View Model offers an alternative approach to handling forms for starting a process and user tasks, especially useful for complex forms typically found in large custom projects. This module provides control over pre-filling, onchange updates, and submissions.

Submission handling covers 2 scenarios:
- When a form is submitted within a `user task`, the task is automatically completed.
- When a form is submitted within a `start form`, the process instance is initiated.

> This module does not create or update cases. Developers are responsible for managing case creation and updates themselves. Commands are recommended for this purpose.
> In short any form of persistence is the responsibility of the developer except for Camunda task completion / Process instance start, this is provided out of the box.

This step-by-step guide will explain the module and demonstrate its implementation.

- Step 1: Enabling the module in your project (see [Enabling the module](enabling-the-module.md))

- Step 2: Define the view-model structure for your form (see [Defining the view-model](defining-the-view-model.md))

- Step 3: Define the submission structure for your form (see [Defining the submission structure](defining-the-submission-structure.md))

- Step 4: Command handling (see [Command handling](command-handling.md))

- Step 5: Error handling (see [Error handling](error-handling.md))
