# How to refer to external data from a form

When creating a form, it can be beneficial to retrieve data that is not normally
accessible from within a form. Form field data resolvers are used to access this
data. These expose prefixes that are used when the form is prefilled by Valtimo (e.g. when
a form is displayed as part of a user task).

Below is an example of how to access external data using a form field data resolver. This assumes
a data resolver which responds to the `example` prefix exists. This assumes there is some kind of
connection between the form and a document (e.g. this form is linked to a user task).

```json
{
    "display": "form",
    
    ...

    
    "components": [
        {
            "label": "firstName",
            "key": "example.firstName",
            "type": "textfield",
            "input": true,
            "validate": {
                "maxLength": 32,
                "unique": false,
                "multiple": false
            }
        },
        ...
    ]
}
```

Information on how to create custom form field data resolvers can be found
[here](/extending-valtimo/form-link/custom-form-field-data-resolver.md).
