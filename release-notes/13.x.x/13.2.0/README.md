---
description: 16-Sep 2025
---

# 13.2.0

**FEATURES**:



* The clickable URL has been added to the widgets&#x20;
* It is possible to switch from task to case directly now
* Added a way of exporting case information. A button is available on the case list screen, next to the create button that allows a user to download all cases that match the current search criteria. In the list column settings columns can be set to exportable. In order for the button to appear, both the new export permission on com.ritense.document.domain.impl.JsonSchemaDocument should be set, and at least 1 exportable column needs to be configured for that case type.
* It is now possible to add a list of actions to each access control permission, making it easier to set up the configuration and keep conditions the same between different permissions.&#x20;
* The quick search functionality has been extended to support user-specific preferences. The feature can store frequently used search queries and applied filters, making repeated searches more efficient. In addition, search results are prioritised based on recent activity and the user’s role within the system, ensuring that the most relevant items are shown first.



**BUG FIXES**:

* The migration issues from valtimo 12 to 13 where migrating forms in MySQL could cause the application to break have been fixed.
* Prevent errors on the case details page by no longer break when related process instances have been deleted (for instance by the history TTL of Camunda).
* An error where the class whitelist for use in scripting (valtimo.camunda.scripting.allowedClasses) did not get properly loaded into the scrip engine has been fixed.
* Some Dutch translations in the confirmation messages have been corrected
* An issue with removal of Case Geometry property has been fixed
* Empty icons show on widget config cards have been improved
* An issue when exporting cases with no status has been resolved
