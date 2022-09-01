# Form Flow

## External data types

This table lists which types of data can be referred to from a form field, and which prefix to use.

| Prefix                        | Type of data                                                                                                    |
|-------------------------------|:----------------------------------------------------------------------------------------------------------------|
| [No prefix](#case-data)       | The data in the document of a case.                                                                             |
| [`oz`](#zaakeigenschappen)    | The 'zaakeigenschappen' stored for the zaak in the Zaken API. Not to be confused with the properties of a zaak. |
| [`pv`](#process-variables)    | Process variables stored for any process instance that is linked to the case                                    |
| [`zaakobject`](#zaakobjecten) | The properties of 'zaakobjecten'. Objects linked to a zaak in the Zaken API                                     |


### Case data
Prefix: No prefix

Uses a reference to data from the json document that stores case data in Valtimo. The dot (`.`) can be used to access
data in nested objects.

Example: `person.firstName`

### Zaakeigenschappen
Prefix: `oz`

Gets the [zaakeigenschap](https://zaken-api.vng.cloud/api/v1/schema/#operation/zaakeigenschap_list) that is indicated in 
the field expression. The available items are defined for a 'zaaktype' in de Catalogi API.

Example: `oz:firstName`

### Process variables
Prefix: `pv`

Accesses process variables for the case for which the form is loaded. It can access all variables of all process 
instances for the case. 

Example: `pv:firstName`

### Zaakobjecten
Prefix: `zaakobject`

In order to use this type the following plugins have to be configured:
- Zaken API
- Objecten API
- Objecttypen API

References a property in a Objecten API object referenced as 'zaakobject'. The field expression contains both the name 
of the 'objecttype' and a JSON Pointer to the property within the JSON store in the zaakobject. There can only be one
object of the requested type linked to the zaak as zaakobject. If no object is found, or multiple objects are found
an exception will be thrown when loading the form. When the object is found, the JSON Pointer is used to find the
property in the JSON stored in the `data` field of the object.

In order for Valtimo to find the correct object, the following needs to be configured correctly:
- A zaak is linked to the current case by using a zaak instance link
- A Zaken API configuration exists that has a base URL matching the zaak instance link URL
- A zaakobject exists in the Zaken API that links the zaak to an object in the Objects API
- An Objecten API configuration exists that has a base URL matching the object URL in the zaakobject
- An Objecttypen API configuration exists that has a base URL matching the type from the object found

Example: `zaakobject:profile:/person/firstName`