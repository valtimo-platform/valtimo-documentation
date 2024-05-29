# Contract validation on ViewModel and Submission

On start up the module will validate that the structure of the `ViewModel` matches the FormDefinition structure of the form. 
This is also done for the submission structure of the form. If not an error message will be printed in the logs.

NOTE: The View Model is used for start-form and user-task forms scenarios. When CamundaTask is not null the form is a user-task form, otherwise it is a start-form.

## ViewModel example:
```kotlin
data class Address(
    val street: String,
    val houseNumber: String,
    val zipCode: String
)

data class Person(
    val firstName: String,
    val lastName: String,
    val fullName: String = "$firstName $lastName",
    val age: Int,
    var personalAddress: Address? = null
) : ViewModel {
    override fun update(submission: T, task: CamundaTask?, businessKey: String): ViewModel {
        // code to update the ViewModel
        return this
    }
}
```

This is the JSON representation of the ViewModel:
```json
{
    "firstName": "John",
    "lastName": "Doe",
    "fullName": "John Doe",
    "age": 25,
    "personalAddress": {
      "street": "Main Street",
      "houseNumber": "123",
      "zipCode": "12345"
    }
}
```

## FormDefinition example:
```json
{
    "display": "form",
    "settings": {
        "pdf": {
            "id": "1ec0f8ee-6685-5d98-a847-26f67b67d6f0",
            "src": "https://files.form.io/pdf/5692b91fd1028f01000407e3/file/1ec0f8ee-6685-5d98-a847-26f67b67d6f0"
        }
    },
    "components": [
        {
            "label": "Firstname",
            "key": "firstName",
            "type": "textfield",
            "input": true
        },
        {
            "label": "Lastname",
            "key": "lastName",
            "type": "textfield",
            "input": true
        },
        {
            "label": "Fullname",
            "key": "fullName",
            "type": "textfield",
            "input": true
        },
        {
            "label": "Age",
            "key": "age",
            "type": "textfield",
            "input": true
        },
        {
            "label": "Container",
            "tableView": false,
            "key": "personalAddress",
            "type": "container",
            "input": true,
            "components": [
                {
                    "label": "Street",
                    "applyMaskOn": "change",
                    "tableView": true,
                    "key": "street",
                    "type": "textfield",
                    "input": true
                },
                {
                    "label": "HouseNumber",
                    "applyMaskOn": "change",
                    "tableView": true,
                    "key": "houseNumber",
                    "type": "textfield",
                    "input": true
                },
                {
                    "label": "ZipCode",
                    "applyMaskOn": "change",
                    "tableView": true,
                    "key": "zipCode",
                    "type": "textfield",
                    "input": true
                }
            ]
        },
        {
            "type": "button",
            "label": "Submit",
            "key": "submit",
            "disableOnInvalid": true,
            "input": true
        }
    ]
}
```

## Validation

The ViewModel list of fields is compared to the FormDefinition list of fields.

List of fields in the ViewModel:
- firstName
- lastName
- fullName
- age
- personalAddress.street
- personalAddress.houseNumber
- personalAddress.zipCode


List of fields in the FormDefinition:
- firstName
- lastName
- fullName
- age
- personalAddress.street
- personalAddress.houseNumber
- personalAddress.zipCode

Here is an example of the error message:
```
The following properties are missing in the view model for form (user-task-2): [age,...]
```
And for submission similar
```
The following properties are missing in the submission for form (user-task-2): [age,...]
```
