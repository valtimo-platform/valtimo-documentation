# Backend libraries 12.1.2

## New Features

The following features were added:

* **Unauthenticated user can now access Actuator health endpoint**

  The Actuator health endpoint (`${management.endpoints.web.base-path}/health`) 
  can now be accessed by an unauthenticated user in either of the following conditions:
  - `management.endpoint.health.show-details` is set to `never`
  - `management.endpoint.health.show-details` is set to `when_authorized` AND 
    `management.endpoint.health.roles` contains `ROLE_ACTUATOR`

## Bugfixes

The following bugs were fixed:

* **Intermediate save on user tasks did not respect the useridentifier setting**

  The user id was used to reference a user for an intermediate save regardless of the useridentifier setting. 
  This has been corrected.

* **Error when user without assign permission opened a user task**

  An error occurred when a user without assign permission opened a user task. 
  The application will no longer attempt to retrieve users when this permission is missing.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
