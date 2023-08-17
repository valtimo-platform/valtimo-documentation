# Backend libraries 10.5.3

## New Features

No new features.

## Bugfixes

The following bugs were fixed:

* **Correctly display special characters in document generated by SmartDocuments**

  The documents generated by SmartDocuments did not display special characters correctly. This has been fixed.

* **Fixed error when generating documents**

  In a rare case, an error was thrown after generating a document with SmartDocuments. This has been fixed.

* **Correctly closing an InputStream**

  After doing a REST call to SmartDocuments, an InputStream would be opened but never closed. This has been fixed.

* **Solved out of memory error**

  Sometimes during the startup phase, an 'Out of memory' error would occur. This was caused by a large number of threads
  that would all start scanning the classpath at the same time. This has been fixed.

## Breaking changes

No breaking changes.

## Deprecations

No deprecations.

## Known issues

No known issues.