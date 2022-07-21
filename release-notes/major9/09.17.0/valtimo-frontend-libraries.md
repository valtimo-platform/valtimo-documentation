# Frontend libraries

## New Features

The following features were added:

* **Saving plugin actions**

  When the form of a new plugin action is filled in on the new process links screen, it can now be saved through the API. When an activity is already linked to a plugin action, clicking on it displays this current configuration, which can then be altered.

* **New field SmartDocuments plugin action 'generate document'**

  The SmartDocuments plugin now takes an extra parameter for the 'generate document' action: 'resultingDocumentProcessVariableName'. The input field for which includes a tooltip.

* **Tooltips in @valtimo/user-interface**

  Tooltip functionality has been added to the input components of the @valtimo/user-interface library.


## Bugfixes

The following bugs were fixed:

* **Sanitization of HTML in timeline component**

  Some HTML icons from the translation assets were not displayed properly, since text on the timeline component is now sanitized before being displayed. These icons have been replaced by text symbols.

## Breaking changes

No known breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.
