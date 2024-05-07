# Backend libraries 11.1.4

## New Features

* **Code called from within BPMN or DMN models is no longer subject to access control checks** 
  Any plugin actions or custom code called from within a BPMN or DMN model will use `runWithoutAuthorization` by default.

* **Provided ZonedLocalDateTimeDeserializer**
  Valtimo Core now ships a custom deserializer for datetime values with zone offset: `ZonedLocalDateTimeDeserializer`.
  Instructions on how to apply this deserializer can be found [here](/reference/modules/core/zoned-localdatetime-deserializer.md).

## Bugfixes

* **Going back in form flows**
  In some specific cases, historic form flow steps would not be cleaned up. This caused error messages when going back to a previous step.

* **Retrieving choicefield values**
  Retrieving choicefield values would throw an error because they were not serializable.

* **Access control permission mapping from task to case**
  Evaluating access control permissions that includes a relation from a CamundaTask to a JsonSchemaDocument would fail and lead to an error.

* **Double escaping of HTML values**
  HTML values were double escaped before showing them in a form.io input field. For more information on how to interpolate data in Form.io forms, see [Interpolating data in Form.io](/using-valtimo/forms/interpolating-data-in-formio.md).

* **Double escaping of HTML values**
  HTML values were double escaped before showing them in a form.io input field. For more information on how to interpolate data in Form.io forms, see [Interpolating data in Form.io](/using-valtimo/forms/interpolating-data-in-formio.md).

## Breaking changes

* Code called from within BPMN or DMN models is no longer subject to access control checks. User information about the user
that initiated the camunda execution is still available through spring security as before.

## Deprecations

No deprecations.

## Known issues

No known issues.
