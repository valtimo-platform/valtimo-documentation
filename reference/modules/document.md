# Documents

## Events

| Event Type                          | When                                     | Description                                                                                                          |
|:------------------------------------|:-----------------------------------------|:---------------------------------------------------------------------------------------------------------------------|
| `DocumentCreatedEvent`              | When a document is created.              | Contains details about the document that was created.                                                                |
| `DocumentDefinitionDeployedEvent`   | When a document definition is deployed.  | Contains details about the deployed document.                                                                        |
| `DocumentFieldChangedEvent`         | -                                        | Not an actual event. It is a part of the `DocumentModifiedEvent` and contains individual changes made to a document. |
| `DocumentModifiedEvent`             | When a document is modified.             | Contains details about each changes when a document is modified.                                                     |
| `DocumentSnapshotCapturedEvent`     | When a document is created or modified.  | Contains a snapshot of the document. Created when a document is created or modified.                                 |
| `DocumentRelatedFileSubmittedEvent` | When a a file is uploaded for a document | Contains the ID of the related document and the resource ID that is being uploaded.                                  |
