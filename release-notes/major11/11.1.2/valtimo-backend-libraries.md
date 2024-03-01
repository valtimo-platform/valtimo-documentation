# Backend libraries 11.1.2

## New Features

* **Code called from within BPMN or DMN models is no longer subject to access control checks** 
  Any plugin actions or custom code called from within a BPMN or DMN model will use `runWithoutAuthorization` by default.

* **Provided ZonedLocalDateTimeDeserializer**
  Valtimo Core now ships a custom deserializer for datetime values with zone offset: `ZonedLocalDateTimeDeserializer`.
  Instructions on how to apply this deserializer can be found [here](zoned-localdatetime-deserializer.md).

## Bugfixes

No bugfixes.

## Breaking changes

* Code called from within BPMN or DMN models is no longer subject to access control checks. User information about the user
that initiated the camunda execution is still available through spring security as before.

## Deprecations

No deprecations.

## Known issues

No known issues.
