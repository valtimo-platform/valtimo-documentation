# Case settings

There are settings that can be set on a case definition level (e.g. whether a case can be assigned). These settings are
using throughout the application to change functionality for that case definition. Currently in Valtimo there is no 
difference between a case definition and a document definition.

## Creating case settings

Case settings can be loaded automatically when creating a case by reading a configuration file. **This file will only
be used when creating a case definition to avoid overriding user configuration.** +

A file should be created on the classpath in the `/config/case/definition` folder. The filename should de the name of 
the document definition and use the `json` file extension. So if there is a document definition with the name `loans` 
then the json file should be named `loans.json.`

```json
{
    "canHaveAssignee": true
}
```

Any value not present in the json file will not be loaded and will instead use the default value.
