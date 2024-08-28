# 🛑 Case search

Valtimo offers an extensive way of searching for cases. This page offers information on how case searches work and how they can be configured.

## Search field configuration file

A search field configuration file can be added to the resource folder. These configurations files are automatically deployed when the application starts.

Configuration files are only automatically deployed when they are located on this path:

`/resource/config/search/`

The name of the configuration file must match the name of the document definition. This ensures that the search field configuration is linked to the correct document definition. For example, if the name of the document definition is `profile`, the configuration file name must be:

`/resource/config/search/profile.json`

The content of the configuration file can look like this:

```json
{
  "searchFields": [
    {
      "title": "Last Name",
      "key": "customerLastName",
      "path": "doc:customer.lastName",
      "dataType": "text",
      "fieldType": "single",
      "matchType": "like"
    }
  ]
}
```

The possible values for the json fields are described [here](configuring-search-fields.md).
