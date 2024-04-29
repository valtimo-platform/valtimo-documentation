# Frontend libraries 10.8.4

## New Features

No new features.

## Bugfixes

The following bugs were fixed:

- **JWT exposed to form.io**
  
  The JWT of the logged-in user was sent to api.form.io when opening a Form.io form. Next to the form building and rendering, Form.io supports a form handling backend with api.form.io as the default domain.
  To retrieve the currently authenticated user, a request would be done to the `/current` endpoint. This behaviour has been changed by explicitly setting the form.io user object, removing the need for this request.
  

## Deprecations

No deprecations.

## Known issues

No known issues.
