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
  "path": "/some/json/path/to/key",
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
            "path": "/path/to/key",
            "dataType": "text",
            "fieldType": "single",
            "matchType": "like"
        }
    ]
}
```

If a specific search field is already present in the database this field is not overwritten. It was probably changed by an
administrator in the user interface, these changes should be kept.

The datatype, fieldtype and matchtype have specific values that are allowed.
You can find the allowed values [here](#allowed-values).

## Get all search fields

To retrieve all the search fields created for a certain document definition use the following endpoint:
`GET /api/v1/document-search/{documentDefinitionName}/fields`. This will return an array of search fields.

## Update existing search field
An existing search field can be updated with new values by calling the following endpoint:
`PUT /api/v1/document-search/{documentDefinitionName}/fields` and providing the following request body:

```json
{
  "title": "title",
  "key": "key_to_search_on",
  "path": "/some/json/path/to/key",
  "dataType": "boolean",
  "fieldType": "single",
  "matchType": "exact"
}
```

The datatype, fieldtype and matchtype have specific values that are allowed.
You can find the allowed values [here](#allowed-values).

## Deleting an existing search field.

An existing search field can be deleted by calling the following endpoint:
`DELETE /api/v1/document-search/{documentDefinitionName}/fields?key={someKey}` and providing both the a query parameter with the 
value of the key that should be deleted.

## Allowed values
The datatype, fieldtype and matchtype only allow specific values. This paragraph will mention all available values
and what the search types do.

### Datatype
The allowed values for datatype are:
* boolean
* date
* datetime
* number
* text

These values determine the type of search that will shown. For example when the datatype is `date` the 
search field will be a datepicker.

### Fieldtype
The allowed values for fieldtype are:
* multiple
* range
* single

The fieldtype value determines how the search should be performed. For example when the fieldtype is `range`
the search field will so from / till fields

### Matchtype
The allowed values for matchtype are:
* exact
* like

The matchtype will determine what type of search is performed. For example when the matchtype is `like` and
the search term is `John` the result will also include a `John Doe`. If the matchtype is `exact` `John Doe` 
will not be part of the result.
