# Backend libraries 12.1.1

## New Features

The following features were added:

* **Fallback scenario for Keycloak migration script (v12.0)**

  In Valtimo 12.0, a script was introduced that migrates the assignees for all user tasks from user-email to user-id.
  In the scenario where the assigned user has been removed from Keycloak the migration script would fail, causing the application to crash on startup.
  In Valtimo 12.1.1, a fallback scenario has been added, unassigning the task and logging the original assignee before continuing.

## Bugfixes

The following bug was fixed:

* **Assigned tasks not visible on the 'my tasks' tab**

  With the introduction of the username/userid as assignee toggle, assigned tasks were not visible on the 'my tasks' tab.
  This bug only occured when the toggle was set to username.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
