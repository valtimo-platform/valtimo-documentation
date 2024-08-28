# Creating FormIO forms in Valtimo

In Valtimo, forms can be prefilled with data from a case or from other external sources. This page describes how

## Value resolvers

Available since 11.0.0

Value resolvers can be used to prefill a form with external data by adding the custom property `sourceKey`:

![Configuring the sourceKey property in a form](../../using-valtimo/forms/img/custom\_source\_key\_property.png)

The following prefixes are supported by default:

* `doc` (Document)
* `pv` (Process variable)

Available since 11.1.0 Value resolvers can also be used to handle submitted form values using the custom property `targetKey`. If the custom property `targetKey` is added, it will store submitted values to the reference provided in the `targetKey`:

![Configuring the targetKey property in a form](../../using-valtimo/forms/img/custom\_target\_key\_property.png)

If a `sourceKey` is provided, it will store submitted values using the reference provided in the `sourceKey`. Unless there is a `targetKey` provided. Then the `targetKey` takes priority.

### ZGW Value resolvers

Valtimo contains additional value resolvers for ZGW services:

* `zaak` (Zaken API)
* `zaakstatus` (Zaken API & Catalogi API)
* `zaakobject` (Zaken API)

More information [here](../../nog-een-plek-geven/reference/modules/form.md#external-data-types)

## Case data

By default, when creating fields in a form the data will be retrieved from and stored in the case. The property of the case that is used depends on the 'Property Name' field on the 'API' tab of the field settings.

> This behaviour has been deprecated as of version 11.0.0 and will be removed in the future. Please use value resolvers instead.

In the example below a document definition is defined with the `firstName` property. A form field is created that corresponds to this property to allow data to be loaded and saved.

Document definition:

```json
{
  "$id": "example.schema",
  "type": "object",
  "title": "Example",
  "$schema": "http://json-schema.org/draft-07/schema#",
  "properties": {
    "firstName": {
      "type": "string",
      "description": "First name"
    }
  }
}
```

Field configuration:

![Configuring the property in a form](../../using-valtimo/forms/img/simple\_key\_field.png)

It is also possible to load properties from an object within the document. In the example below the document definition contains an object 'person', that has a 'firstName' property. This property can be accessed by using `person.firstName` as the field property name.

Document definition:

```json
{
  "$id": "example.schema",
  "type": "object",
  "title": "Example",
  "$schema": "http://json-schema.org/draft-07/schema#",
  "properties": {
    "person": {
      "type": "object",
      "properties": {
        "firstName": {
          "type": "string",
          "description": "First name"
        }
      }
    }
  }
}
```

Field configuration:

![Configuring the property in a form](../../using-valtimo/forms/img/nested\_key\_field.png)

## External data

> This feature has been deprecated as of version 11.0.0 and will be removed in the future. Please use value resolvers instead.

In some cases there is other data related to the case, but not part of the document that needs to be displayed in a form. The form module allows for `FormFieldDataResolver` to fetch data by using expressions as property name in forms. On loading the form the data is automatically preloaded. The expression generally looks like `<prefix>:<field-expression>` where the prefix indicates which `FormFieldDataResolver` is used. The `<field-expression>` in this expression gives the resolver information on what data to load. For example, when using the expression `openzaak:firstName` for a field, the `OpenZaakFormFieldDataResolver` is used to access the zaakeigenschappen in the Zaken API and get the `firstName` property.

Even though technically a `FormFieldDataResolver` is not used, the prefix `pv` is available to access the process variables in functionally the same way. For example, the expression `pv:age` would try to get the 'age' variable from the process variables.

A list of `FormFieldDataResolvers` that are available on the [forms reference page](../../nog-een-plek-geven/reference/modules/form.md#external-data-types).

A description on how to create a new `FormFieldDataResolver` is available on the [creating form data resolver page](forms/creating-form-field-data-resolver.md)

## Disable prefilling of fields

Prefilling can be disabled for specific input fields by configuring a `prefill` property in the JSON of the form definition as follows:

```json
{
  "display": "form",
  "components": [
    {
      "key": "firstName",
      "type": "textfield",
      "input": true,
      "prefill": false
    }
  ]
}
```

## Disabled fields

Disabled form fields are prefilled and saved by default. This behaviour deviates from the web-standard where disabled elements are not included in the submit body.

This behaviour can be changed by setting a toggle in application.yml:

```yaml
valtimo:
    form:
      ignoreDisabledFields: true
```

When set to true, disabled fields will no longer be prefilled or saved. The default value is false.

## Disabling prefill

Available since 10.5.0

In some cases it is desirable to be able to disable a form input prefill. For example, an upload input might result in duplicate files when prefilled.

To disable prefilling a component, the `prefill` property can be set in the FormIO definition:

```json
{
  "key": "file-attachments",
  "type": "valtimo-file",
  "input": true,
  "label": "Relevant files",
  "prefill": false,
  ...
}
```

In contrast to [Disabled fields](creating-forms-in-valtimo.md#disabled-fields), setting this property to false will still save the result in the document.

## Translations

To display forms in different languages, we can utilize translations. This involves translating all the labels based on their label property, and using a function `instance.t('translationKey')` to display content from the translation file inside the htmlContent.

An example of a translated form.io definition:

```json
{
  "display": "form",
  "components": [
    {
      "key": "html",
      "type": "htmlelement",
      "input": false,
      "label": "HTML",
      "content": "<p>{{ instance.t('contentX') }}</p>",
      "tableView": false,
      "refreshOnChange": false
    },
    {
      "key": "isApproved",
      "type": "radio",
      "input": true,
      "label": "configurationApproved",
      "inline": false,
      "values": [
        {
          "label": "yes",
          "value": "true",
          "shortcut": ""
        },
        {
          "label": "no",
          "value": "false",
          "shortcut": ""
        }
      ],
      "default": true,
      "tableView": false,
      "defaultValue": false,
      "optionsLabelPosition": "right"
    },
    {
      "key": "comment",
      "type": "textarea",
      "input": true,
      "label": "comment",
      "tableView": true,
      "autoExpand": false
    },
    {
      "key": "send",
      "type": "button",
      "input": true,
      "label": "send",
      "tableView": false,
      "customClass": "float-right",
      "saveOnEnter": false,
      "showValidations": false
    }
  ]
}
```

Where form.io definition is using the following translation properties:

```json
{
  "formioTranslations": {
    "contentX": "This is content text which is set by the instance.t() function",
    "ConfigurationApproved": "Configuration approved?",
    "yes": "Yes",
    "no": "No",
    "comment": "Comment",
    "send": "Send"
  }
}
```

Which results in: ![Configuring the property in a form](../../using-valtimo/forms/img/form\_io\_translations.png)
