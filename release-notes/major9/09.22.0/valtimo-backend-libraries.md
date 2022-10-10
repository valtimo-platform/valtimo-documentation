# Backend libraries 9.22.0 (RC)

## New Features

The following features were added:

* **Allow external fields to have a nested formfield.key structure**

  Previously an external field definition only supported 1 level keys like:
  - `ex.keyName`

  Now its possible to define nested stuctures like:
  - `ex.keyName.anotherKeyName`
    Resulting in structures that can be mapped into the prefilling/submission phase:
   ```json
   {
       "ex" : {
           "keyName" : {
                "anotherKeyName" : "someValue"
           }
       }
   }
  ```

* **New feature2**

  Description of the new feature goes here.
  Also link to the page that explains the feature in greater detail.


## Bugfixes

The following bugs were fixed:

* **SonarQube issues**

  SonarQube scanned the backend code for bugs and vulnerabilities. SonarQube found:
  - 21 Bugs
  - 7 Vulnerabilities

  All bugs and vulnerabilities that SonarQube found have been solved.


* **Bug2**

  Description of what the issue was.

## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **Deprecation1**

  X was deprecated and is replaced with Y.

* **Deprecation2**

  X was deprecated and is replaced with Y.

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Issue1**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue

* **Issue2**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue
