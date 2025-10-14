# 📋 Forms

Valtimo uses the [Form.io](https://www.form.io/) form builder to create forms that can be used for multiple purposes, such as:

* Task forms
* Process start forms
* Case detail view

## Translations

Translations are supported in the form.io definitions. Any translations available [from configured translation resources](../localization/configuring-localization.md)
in your implementation can be used.

To have something in your form translated, use the following syntax: `translate:translationKey`.

This can be used inside anywhere in the form definition, including inside HTML.

When the form is rendered, the translation will be resolved and displayed.

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
      "content": "<p>translate:formioTranslations.contentX</p>",
      "tableView": false,
      "refreshOnChange": false
    },
    {
      "key": "isApproved",
      "type": "radio",
      "input": true,
      "label": "translate:formioTranslations.configurationApproved",
      "inline": false,
      "values": [
        {
          "label": "translate:formioTranslations.yes",
          "value": "true",
          "shortcut": ""
        },
        {
          "label": "translate:formioTranslations.no",
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
      "label": "translate:formioTranslations.comment",
      "tableView": true,
      "autoExpand": false
    },
    {
      "key": "send",
      "type": "button",
      "input": true,
      "label": "translate:formioTranslations.send",
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

Which results in:

<figure><img src="../../using-valtimo/forms/img/form_io_translations.png" alt=""><figcaption></figcaption></figure>
