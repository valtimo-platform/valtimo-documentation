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

* **Filtering Form Flow submissiondata is now configurable**
  
  In Valtimo 12.1.0, a filter has been introduced on the submissiondata of a Form Flow step. Any data that is not included in the form.io definition, will be filtered out.
  To prevent breaking Form Flows that intentionally use data that is not part of the form.io definition, this filter is now configurable.
  The `valtimo.formFlow.doSubmissionDataFiltering` property can be set to false to disable the filter.

* **Assigned tasks not visible on the 'my tasks' tab of the filtered task list**

  With the introduction of the username/userid as assignee toggle, assigned tasks were not visible on the 'my tasks' tab of the filtered task list.
  This bug only occured when the toggle was set to username.

  

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
