# 13.5.0

## New Features

* **Performance improvements**

Significant performance improvements when retrieving tasks and cases, smaller performance improvements everywhere else.

* **Improved logging for developers**

This release includes an internal improvement to how Valtimo logs request and response data.  
When working with JSON-based integrations, log entries are now automatically formatted to be easier to read.

* **Improved Notificaties API logging**

When an abonnement cannot be registered or updated with the Notificaties API, additional information is provided on
what went wrong.

## Enhancements

* **Updated dependencies**

  The following dependencies were updated:
  * Operaton (`1.0.0-beta-4` &rarr; `1.0.0-rc-1`)
  * Everit Json Schema (`1.14.5` &rarr; `1.14.6`)
  * Commons Validator (`1.9.0` &rarr; `1.10.0`)
  * Guava (`33.4.8-jre` &rarr; `33.5.0-jre`)

## Bugfixes

* Process links referencing forms are now always copied properly when creating a new draft version of an existing case definition.
* Case tags and header widgets are now copied when creating a new draft version of an existing case definition.
