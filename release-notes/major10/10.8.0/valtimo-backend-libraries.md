# Backend libraries 10.8.0

## New Features

The following features were added:

* **Added properties to portaal taak**

  When a portaal taak is created through the portaaltaak plugin, the 'verloopdatum' and 'zaak' properties are included in the object. 
  - The 'verloopdatum' property is calculated based on the configured 'verloopDurationInDays'
  - The 'zaak' property includes the full URL to the Zaak, if present

## Bugfixes

The following bugs were fixed:

* **Task candidate users list was incomplete**

  The candidate-user list of a user task was incomplete for tasks with multiple candidate groups. In this case, the candidate-user list would only contain users based on the first candidate group.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
