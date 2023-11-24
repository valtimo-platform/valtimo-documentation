# CloudEvents

## Available CouldEvents

This table shows all available CloudEvents in Valtimo.

| Event name                             | Content type                                                |
|----------------------------------------|:------------------------------------------------------------|
| **DocumentCreated**                    | `com.ritense.document.domain.impl.JsonSchemaDocument`       |
| **DocumentUpdated**                    | `com.ritense.document.domain.impl.JsonSchemaDocument`       |
| **DocumentViewed**                     | `com.ritense.document.domain.impl.JsonSchemaDocument`       |
| **TaskCompleted**                      | `com.ritense.valtimo.camunda.domain.CamundaTask`            |
| **DocumentStored**                     | `com.ritense.documentenapi.client.CreateDocumentResult`     |
| **DocumentInformatieObjectViewed**     | `com.ritense.documentenapi.client.DocumentInformatieObject` |
| **DocumentInformatieObjectDownloaded** | N/A                                                         |
| **DocumentLinkedToZaak**               | `com.ritense.zakenapi.client.LinkDocumentResult`            |
| **ZaakObjectenListed**                 | `List<com.ritense.zakenapi.domain.ZaakObject>`              |
| **ZaakInformatieObjectenListed**       | `List<com.ritense.zakenapi.domain.ZaakInformatieObject>`    |
| **ZaakRollenListed**                   | `List<com.ritense.zakenapi.domain.rol.Rol>`                 |
| **ZaakRolCreated**                     | `com.ritense.zakenapi.domain.rol.Rol`                       |
| **ZaakCreated**                        | `com.ritense.zakenapi.domain.CreateZaakResponse`            |
| **ZaakStatusCreated**                  | `com.ritense.zakenapi.domain.CreateZaakStatusResponse`      |
| **ZaakResultaatCreated**               | `com.ritense.zakenapi.domain.CreateZaakResultaatResponse`   |
| **ZaakOpschortingUpdated**             | `com.ritense.zakenapi.domain.ZaakopschortingResponse`       |
| **ZaakViewed**                         | `com.ritense.zakenapi.domain.ZaakResponse`                  |
| **ObjectViewed**                       | `com.ritense.objectenapi.client.ObjectWrapper`              |
| **ObjectCreated**                      | `com.ritense.objectenapi.client.ObjectWrapper`              |
| **ObjectUpdated**                      | `com.ritense.objectenapi.client.ObjectWrapper`              |
| **ObjectPatched**                      | `com.ritense.objectenapi.client.ObjectWrapper`              |
| **ObjectDeleted**                      | N/A                                                         |
| **NoteCreated**                        | `com.ritense.document.domain.Note`                          |
| **NoteUpdated**                        | `com.ritense.document.domain.Note`                          |
| **NoteDeleted**                        | N/A                                                         |
| **NotesListed**                        | `List<com.ritense.document.domain.Note>`                    |
