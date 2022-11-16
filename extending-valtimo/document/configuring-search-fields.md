# Search fields

Search fields add the ability to filter cases. Each search field adds the ability to filter on a specific field.
This page describes how the search fields can be created, read, updated and deleted.

## Creating search fields

There are two methods available to create a search field:

1) Using the endpoint `POST /api/v1/document-search/{documentDefinitionName}/fields` and providing the following request body:

```json
{
  "title": "title",   
  "key": "key_to_search_on",
  "path": "doc:path.to.key",
  "dataType": "date",
  "fieldType": "range",
  "matchType": "exact"
}
```

2) Using auto deployment. Create a json file with the same name as a document definition in `/config/search/`. So if there is
a document definition with the name `loans` then the json file should be named `loans.json.` The content of the json file
should have the following structure:

```json
{
    "searchFields": [
        {
            "title": "title",
            "key": "key",
            "path": "doc:path.to.key",
            "dataType": "text",
            "fieldType": "single",
            "matchType": "like"
        }
    ]
}
```

If a specific search field is already present in the database this field is not overwritten. It was probably changed by an
administrator in the user interface, these changes should be kept.

The `dataType`, `fieldType` and `matchType` only allow for specific values. A list of these allowed values can be
found [here](#allowed-values).

## Get all search fields

To retrieve all the search fields created for a certain document definition use the following endpoint:
`GET /api/v1/document-search/{documentDefinitionName}/fields`. This will return an array of search fields.

## Update existing search field

Existing search fields can be updated with new values by using the endpoint below. The endpoint below accepts a list of
search fields. The ordering of search fields in this list is preserved.
`PUT /api/v1/document-search/{documentDefinitionName}/fields` and providing the following request body:

```json
[
  {
    "title": "title",
    "key": "key_to_search_on",
    "path": "doc:path.to.key",
    "dataType": "boolean",
    "fieldType": "single",
    "matchType": "exact"
  }
]
```

The `dataType`, `fieldType` and `matchType` only allow for specific values. A list of these allowed values can be
found [here](#allowed-values).

## Deleting an existing search field.

An existing search field can be deleted by calling the following endpoint:
`DELETE /api/v1/document-search/{documentDefinitionName}/fields?key={someKey}` and providing both a query parameter with the 
value of the key that should be deleted.

## Allowed values

The `dataType`, `fieldType` and `matchType` only allow for specific values. This paragraph will mention all available
values and what the search types do.

### Data type
The allowed values for `dataType` are:
* boolean
* date
* datetime
* number
* text

These values determine the type of search that will show. For example when the `dataType` is `date` the 
search field will be a datepicker.

### Field type
The allowed values for `fieldType` are:
* multiple
* range
* single

The `fieldType` value determines how the search should be performed. For example when the `fieldType` is `range`
the search field will so from / till fields

### Match type
The allowed values for `matchType` are:
* exact
* like

The `matchType` will determine what type of search is performed. For example when the `matchType` is `like` and
the search term is `John` the result will also include a `John Doe`. If the `matchType` is `exact` `John Doe` 
will not be part of the result.
