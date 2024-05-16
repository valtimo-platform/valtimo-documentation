# Defining the view-model

Before you can start implementing your view-model we need to define what that is.

## What is a view-model?

view-model: A data model that serves as a bridge between the form and the BE so that you can prefill/update/validate form data.

![diagram](svg/view-model-diagram.svg)

## How to define a view-model

A view-model is a data class that implements the `ViewModel` interface. The interface has a single method `update()` that is used to update the view-model based on the data that is passed to it.

The `update()` method is triggered when the update endpoint is called. This endpoint is called automatically when a change is made in the form.

```kotlin
data class TestViewModel(
    val firstName: String,
    val lastName: String,
    val fullName: String = "$firstName $lastName",
    val age: Int,
    var adultPermissionRequired: Boolean = false
) : ViewModel {
    override fun update(): ViewModel {
        if (this.age!! < 18) {
            this.adultPermissionRequired = true
        }

        return this
    }
}
```

After you define a `ViewModel` you also need to define a loader.

## How to define a loader

A `ViewModelLoader` is a class that is used to load the view-model.

The `load()` method is used to load the view-model the `taskInstanceId` to use process variable.

The `supports()` method is used to find the correct loader for the given form.

The `getFormName()` method is used to get the form name.

The generic type that is passed to the `ViewModelLoader` is used for validating the `ViewModel` on start-up.

The `ViewModelLoader` also needs to be registered as a bean in the Spring context.
```kotlin
@Component
class TestViewModelLoader : ViewModelLoader<TestViewModel> {
    override fun load(taskInstanceId: String): TestViewModel {
        return TestViewModel(
            firstName = "",
            lastName = "",
            age = 0
        )
    }

    override fun supports(formName: String): Boolean {
        return formName == getFormName()
    }

    override fun getFormName(): String = "test"
}
```

## Contract validation
On start up a class will validate that the structure of the `ViewModel` matches the submission structure of the form. If not an error message will be printed in the logs. Note that extra properties may be included in the form.

Here is an example of the error message:
```
The following properties are missing in the view model for form (user-task-2): [age]
```

More info on the validation can be found here: [Contract validation on ViewModel and Submission](contract-validation.md)
