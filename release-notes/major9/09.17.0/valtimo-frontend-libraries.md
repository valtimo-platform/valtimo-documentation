# Frontend libraries 5.5.0

## New Features

The following features were added:

* **Saving process links**

  When the form of a new plugin action is filled in on the new process links screen, it can now be saved through the
  API. When an activity already has a process link, clicking on it displays this process link, which
  can then be altered. More information on plugins can be found [here](/using-valtimo/plugin/create-process-link.md).

* **New field SmartDocuments plugin action 'generate document'**

  The SmartDocuments plugin now takes an extra parameter for the 'generate document' action:
  'resultingDocumentProcessVariableName'. This plugin stores the generated document locally, and other plugins can be
  used to send it to another service.

* **Tooltips in @valtimo/user-interface**

  Tooltip functionality has been added to the input components of the `@valtimo/user-interface` library.


## Bugfixes

The following bugs were fixed:

* **Sanitization of HTML in timeline component**

  Some HTML icons from the translation assets were not displayed properly, since text on the timeline component is now
  sanitized before being displayed. These icons have been replaced by text symbols.

## Breaking changes

No known breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
