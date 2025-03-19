# Form

## External data types

This table lists which types of data can be referred to from a form field, and which prefix to use.

| Prefix                                  | Type of data                                                                                                    |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| [No prefix](form.md#case-data)          | The data in the document of a case.                                                                             |
| [`openzaak`](form.md#zaakeigenschappen) | The 'zaakeigenschappen' stored for the zaak in the Zaken API. Not to be confused with the properties of a zaak. |
| [`pv`](form.md#process-variables)       | Process variables stored for any process instance that is linked to the case                                    |
| [`zaak`](form.md#zaakobjecten)          | The properties of a zaak in the Zaken API                                                                       |
| [`zaakstatus`](form.md#zaakobjecten)    | The properties of 'zaakstatus' linked to a zaak in the Zaken API                                                |
| [`zaakobject`](form.md#zaakobjecten)    | The properties of 'zaakobjecten'. Objects linked to a zaak in the Zaken API                                     |

### Case data

Prefix: No prefix

Uses a reference to data from the json document that stores case data in Valtimo. The dot (`.`) can be used to access data in nested objects.

Example: `person.firstName`

### Zaakeigenschappen

Prefix: `openzaak`

Gets the [zaakeigenschap](https://zaken-api.vng.cloud/api/v1/schema/#operation/zaakeigenschap_list) that is indicated in the field expression. The available items are defined for a 'zaaktype' in de Catalogi API.

Example: `openzaak:firstName`

### Process variables

Prefix: `pv`

Accesses process variables for the case for which the form is loaded. It can access all variables of all process instances for the case.

Example: `pv:firstName`

### Zaak

Available since 11.2.0

Prefix: `zaak`

With the `zaak` prefix, all data inside a [zaak response](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/zaken-api/master/src/openapi.yaml#tag/zaken/operation/zaak_create) can be used to prefill the form. Some examples:

| Source key         | Type of data                                            | Example                                                                         |
| ------------------ | ------------------------------------------------------- | ------------------------------------------------------------------------------- |
| zaak:url           | A URL reference to the zaak                             | https://example.com/zaken/api/v1/zaken/f4086828-b0b7-4e6c-a0ac-5ca1e44c5b06     |
| zaak:uuid          | Zaak UUID                                               | f4086828-b0b7-4e6c-a0ac-5ca1e44c5b06                                            |
| zaak:identificatie | The zaak identifier                                     | ZK2023-00001                                                                    |
| zaak:startdatum    | The date at which the execution of the zaak was started | 2023-12-12                                                                      |
| zaak:status        | A URL reference to the zaak status                      | https://example.com/zaken/api/v1/statussen/8265450b-9a96-4948-8a0f-eb40a26f7aea |

### Zaakstatus

Available since 11.2.0

Prefix: `zaakstatus`

With the `zaakstatus` prefix, all data inside a [zaak statustypen response](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/VNG-Realisatie/catalogi-api/master/src/openapi.yaml#tag/statustypen/operation/statustype_retrieve) can be used to prefill the form. Some examples:

| Source key                      | Type of data                      | Example                                                                         |
| ------------------------------- | --------------------------------- | ------------------------------------------------------------------------------- |
| zaakstatus:url                  | A URL reference to the zaakstatus | https://example.com/zaken/api/v1/statussen/8265450b-9a96-4948-8a0f-eb40a26f7aea |
| zaakstatus:omschrijvingGeneriek | Zaak status description           | Intake finished                                                                 |
| zaakstatus:volgnummer           | The status trace number           | 2                                                                               |

### Zaakobjecten

Prefix: `zaakobject`

In order to use this type the following plugins have to be configured:

* Zaken API
* Objecten API
* Objecttypen API

References a property in a Objecten API object referenced as 'zaakobject'. The field expression contains both the name of the 'objecttype' and a JSON Pointer to the property within the JSON store in the zaakobject. There can only be one object of the requested type linked to the zaak as zaakobject. If no or multiple objects are found, an exception will be thrown when loading the form. When the object is found, the JSON Pointer is used to find the property in the JSON stored in the `data` field of the object.

In order for Valtimo to find the correct object, the following needs to be configured correctly:

* A zaak is linked to the current case by using a zaak instance link
* A Zaken API configuration exists that has a base URL matching the zaak instance link URL
* A zaakobject exists in the Zaken API that links the zaak to an object in the Objects API
* An Objecten API configuration exists that has a base URL matching the object URL in the zaakobject
* An Objecttypen API configuration exists that has a base URL matching the type from the object found

Example: `zaakobject:profile:/person/firstName`
