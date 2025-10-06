
# 13.3.0

## Bugfixes

* Case widgets of type FormIO will now correctly finish loading and no longer cause the widget
  page to be stuck on a loading animation.
* Fixed an issue where the Verzoek plugin could not be migrated correctly which caused the
  `VerzoekProperties["caseDefinitionKey"]` to be `NULL`.
