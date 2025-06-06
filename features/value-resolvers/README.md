# 🔢 Value resolvers

Value resolvers provide a framework to retrieve and/or store data at several sources like processvariables (pv:), documents (doc:) and more.

Custom resolvers can be created for external sources.

## Supported value resolvers

| Data                  | Description                                                         | Prefix  | Postfix                            | Example               |
| --------------------- | ------------------------------------------------------------------- | ------- | ---------------------------------- | --------------------- |
| **Case JSON data**    | Resolves values from the JSON content of the JsonSchemaDocument     | `doc:`  | Json path to a field               | doc:person.firstName  |
| **Case columns**      | Resolves values from the database columns of the JsonSchemaDocument | `case:` | database column name in camel case | case:assigneeFullName |
| **Process variables** | Resolves values form the Camunda BPMN process variables             | `pv:`   | Process variable name              | pv:lastName           |

## ZGW value resolvers

| Data                     | Description                                            | Prefix        | Postfix                                                                                                                                                                                                                           | Example                              |
| ------------------------ | ------------------------------------------------------ | ------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------ |
| **Zaken API zaak**       | Resolves values from the Zaken API zaak response       | `zaak:`       | Name of the field from the [zaak response](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/zaken-api/master/src/openapi.yaml#tag/zaken/operation/zaak\_create)                              | zaak:identificatie                   |
| **Zaken API zaakstatus** | Resolves values from the Zaken API zaakstatus response | `zaakstatus:` | Name of the field from the [zaak statustypen response](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/catalogi-api/master/src/openapi.yaml#tag/statustypen/operation/statustype\_retrieve) | zaakstatus:omschrijvingGeneriek      |
| **Zaken API zaakobject** | Resolves values form the Zaken API zaakobject          | `zaakobject:` | The object type and a reference to a property                                                                                                                                                                                     | zaakobject:profile:/person/firstName |
