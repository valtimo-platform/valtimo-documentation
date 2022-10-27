# Case search

## Search field configuration file

A search field configuration file can be added to the resource folder. These configurations files are automatically
deployed when the application starts.

Configuration files are only automatically deployed when they are located on this path:

`/resource/config/search/`

The name of the configuration file must match the name of the document definition. This ensures that the search field
configuration is linked to the correct document definition. For example, if the name of the document definition
is `profile`, the configuration file name must be:

`/resource/config/search/profile.json`

The content of the configuration file can look like this:

```json
{
  "searchFields": [
    {
      "key": "customerLastName",
      "path": "/customer/lastName",
      "dataType": "text",
      "fieldType": "single",
      "matchType": "like"
    }
  ]
}
```

**key**

This is an identifying human-readable key of the field.

**path**

The path pointing to the property that we want to search for. This field is optional.

**dataType**

The data type of the property that we want to search for. The options are limited to: text, number, date, datetime and
boolean.

**fieldType**

There are three field types: single, multiple, range. When a search field is configured to have the 'single' field type,
a user can only search for one value at once. With the 'multiple' field type, a user can search for multiple
values and with the 'range' field type, a user can search for a range of values.

**matchType**

There are two match types: exact and like. With the 'exact' match type, a user can only find cases that match exactly
the search query. For example, if a user searches for cases with a last name property value 'Doe', it will not return
cases that have a last name 'Doely'. But, when the match type 'like' is used, both cases with 'Doe' and 'Doely' are
returned.
