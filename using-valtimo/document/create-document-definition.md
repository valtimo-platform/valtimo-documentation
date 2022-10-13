# Creating a document definition

A document definition is a JSON document that defines the structure that document has, as well as restrict the allowed
values for each property through validation rules. This page shows how to create a document definition, and how to add
validation to properties. How to create a process with a document can be found [here](start-case.md).

### Prerequisites

This page requires you to have knowledge of JSON schema.

## Definition

To create a document definition, the following steps are necessary:

* Create a document definition file (ending with `.schema.json`) under the following path: 
  `*/resources/config/document/definition`. The name should correspond with the ID of the document ID. The ID itself
  should end with `.schema`.

  #### **`person.schema.json`**

  ```json
  {
    "$id": "person.schema",
    "$schema": "http://json-schema.org/draft-07/schema#",
    "title": "Person",
    "type": "object",
    "properties": {
    }
  }
  ```

* Properties as well as validation rules can be added to the definition as per the JSON schema standard as seen
  [here](https://json-schema.org/understanding-json-schema/index.html). Below is an example of what this definition could
  look like.

  ```json
  {
    "$id": "person.schema",
    "$schema": "http://json-schema.org/draft-07/schema#",
    "title": "Person",
    "type": "object",
    "properties": {
      "firstName": {
        "type": "string",
        "description": "The person's first name.",
        "maxLength": 15
      },
      "age": {
        "description": "Age in years which must be equal to or greater than zero.",
        "type": "integer",
        "minimum": 0
      },
      "birthday": {
        "description": "Birthday",
        "type": "string",
        "format": "date"
      },
      "hasPet": {
        "description": "Has pet.",
        "type": "boolean"
      }
    }
  }
  ```

### Uploading a document definition

As an alternative to creating a document definition in the project, a document definition can also be uploaded via the
admin interface. Creating the file itself is identical, but the path is not important as it will be uploaded to Valtimo.

* Go to the menu 'Admin'.
* Go to the menu 'Cases'.
* Click on 'Upload case-definition'.
* Upload the document definition.

![Uploading a document definition](img/upload-document-definition.png)
