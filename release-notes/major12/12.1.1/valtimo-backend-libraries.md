# Backend libraries 12.1.1

## New Features

The following features were added:

* **Fallback scnario for Keycloak migration script (v12.0)**

  In Valtimo 12.0, a script migrates the assignees for all user tasks from user-email to user-id.
  In the scenario where the assigned user has been removed from Keycloak the migration script would fail, causing the application to crash on startup.
  In Valtimo 12.1.1, a fallback scenario has been implemented, unassigning the task and logging the original assignee before continuing.

## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
