# Documents

A document is the starting point of the case and the main data storage for that case.

One or multiple processes can be associated with a document. One process is needed to create the document, other processes can be started for already existing documents.

The document content is predefined in a document definition, and each property defined can contain validation rules. That way, Valtimo enforces the correctness of the document as much as possible. For document definitions, JSON schema is used. The complete documentation for JSON schema can be found
[here](https://json-schema.org/understanding-json-schema/index.html).

Users interact with the document via user tasks: document data can be loaded into task forms, and user input can be stored in the document after completing a task.
