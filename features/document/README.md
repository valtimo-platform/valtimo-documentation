# 📃 Documents

A document is the starting point of the case and the main data storage for that case.

One or multiple processes can be associated with a document. At least one process needs to be linked to a case to be able to create the document; other processes can be configured to either create the document or to contribute to an existing document.

The document content is defined in a document definition, each property defined can contain validation rules. That way, Valtimo enforces the correctness of the document as much as possible. For document definitions, JSON schema is used. The complete documentation for JSON schema can be found [here](https://json-schema.org/understanding-json-schema/index.html).

Users interact with the document via user tasks. A user task can be linked to a task form that can preload document data, and user input from a task form can be stored in the document after completing a task. By completing a task the data is validated against the validation rules of the document definition and stored.

Document data can be presented in the UI as a case by preloading the data into multiple forms for that case.

This section contains information on how to configure and use Documents in Valtimo.

* [Custom case list columns](../case/for-developers/custom-case-list-columns.md)
* [Custom case headers](../case/for-developers/custom-case-headers.md)
* [Assigning a user to a document](assigning-a-user.md)

