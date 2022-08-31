# Documents

Every process in Valtimo requires a document in order to run, which stores related data to a case. The contents for this
document are predefined in a document definition, and each property defined in there definition contain validation
rules. Documents can be used in processes in order to make service calls, to prefill forms, store form results, etc.

One document can be used by multiple process instances (e.g. when a process instance is created in a call activity), as
long as the parent process is linked to the document and the business key of this process corresponds to the document.

For document definitions, JSON schema is used. The complete documentation for JSON schema can be found
[here](https://json-schema.org/understanding-json-schema/index.html).
