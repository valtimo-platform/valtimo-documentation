# Backend libraries 10.8.0

## New Features

The following features were added:

* **Added more information to portaal taak**

- When a portaal taak is created through the portaaltaak plugin, a due date and a link to the related zaak
is included in the object.


## Bugfixes

The following bugs were fixed:

* **Task candidate users list was incomplete**

  The list of assignees for a user task is no longer incomplete. The bug happened when the user task was configured to
  have more than one role in the candidate groups. The list of assignees would only contain users for the first role in
  the candidate groups.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
