# Auto deploying case tabs

Case tabs can be auto-deployed from a json file at startup. This is useful to keep the case tab configuration identical
across multiple environments. Case tabs are auto-deployed by scanning files on the classpath that end
in `.case-tab.json`.

### Changesets

Every deployment file for represents a changeset. These files are required to contain a changesetId that should be
unique over all deployment files that use changesets. When starting up, changesets that have already been executed will
be ignored. A checksum of the changeset is created when it is executed. Changesets that have already been deployed
should not change. Changesets that have been changed since a previous time will result in an error and failure to start
the application.

All changesets can be executed again, even when the content has changed, by setting
the `valtimo.changelog.case-tabs.clear-tables` property to `true`.

### Example

You can find an example of the JSON below.

In this example a tab is created with type `standard`. Different tab types can be used to customize the tab. The types
that are available can be found on the [reference page](/reference/modules/case.md#case-tabs-types).

```json
{
    "changesetId": "my-case-definition-name-tabs-v1",
    "case-definitions": [
        {
            "key": "my-case-definition-name",
            "tabs": [
                {
                    "name": "Summary",
                    "key": "summary",
                    "type": "standard",
                    "contentKey": "summary"
                },
                {
                    "name": "Progress",
                    "key": "progress",
                    "type": "standard",
                    "contentKey": "progress"
                },
                {
                    "name": "Zaak objects",
                    "key": "zaakobjecten",
                    "type": "standard",
                    "contentKey": "zaakobjecten"
                }
            ]
        }
    ]
}
```
