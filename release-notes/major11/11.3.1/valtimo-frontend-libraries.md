# Frontend libraries 11.3.1

## New Features

No new features.

## Bugfixes

The following bugs were fixed:

- **Empty strings are sent as 'null' in process link configurations**
  
  There was a difference in creating a new process link configuration and changing an existing one. 
  In both scenario's, empty strings are now sent as 'null' to the backend to prevent different behaviour.

## Deprecations

No deprecations.

## Known issues

No known issues.
