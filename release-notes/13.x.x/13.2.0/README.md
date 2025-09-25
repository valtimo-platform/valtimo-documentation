# 13.2.0

## New Features

#### Direct navigation from a task to associated case

In the Task modal opened from the Task list, a folder details icon is now displayed. Selecting this icon opens the associated case in a new tab.

#### Value path selector

The case definition dropdown has been removed to simplify the configuration of document definition names. The value path selector behavior now adapts to the context:

* Inside a Case: The case definition dropdown has been removed. Users can directly choose a path from the current case, either by selecting from the available paths in the dropdown or by entering it manually.
<figure><img src="../../../.gitbook/assets/value-path-selector-inside-case.png.png" alt=""><figcaption></figcaption></figure>

* Outside a Case: The Value Path Selector is replaced with a simple text input field for manual entry. In this context, the toggle between dropdown and input field is no longer available.
<figure><img src="../../../.gitbook/assets/value-path-selector-outside-case.png.png" alt=""><figcaption></figcaption></figure>

#### Widgets display clickable URLs

Widget cards now surface their associated URLs as clickable links, making it easier to follow through to the referenced page.

#### Exporting case information

An export button is available on the case list screen, next to the create button. The button appears when the export permission on `com.ritense.document.domain.impl.JsonSchemaDocument` is granted and at least one column is marked as exportable within the list column settings.

#### Access control actions

Each access control permission can now include a list of actions, allowing a single permission to govern multiple related operations while keeping conditions in sync.

#### Quick search improvements

Quick search learns from each user by storing frequently used queries and filters. Results are prioritised using recent activity and the user's role, surfacing the most relevant items first.

## Bug fixes

* Migration issues from Valtimo 12 to 13 that could break MySQL form migrations have been resolved.
* The case details page no longer errors when related process instances have been deleted (for example by Camunda's history TTL).
* The `valtimo.camunda.scripting.allowedClasses` whitelist now loads correctly into the script engine.
* Several Dutch confirmation message translations have been corrected.
* Removing the Case Geometry property now works as expected.
* Widget configuration cards no longer display empty icons.
* Exporting cases without a status now completes without errors.
