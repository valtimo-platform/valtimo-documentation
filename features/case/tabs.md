# Tabs

Case tabs are the tabs that are shown on the case detail page. They are used to break up the information of a case into logical categories. The tabs that are shown can be configured per case type.

![Example of case tabs for a case](../../using-valtimo/case/img/case-tab-example.png)

By default, each newly created case type has a number of tabs that are preconfigured:

* Summary
* Progress
* Audit
* Documents
* Notes

## Enabling case tabs

To enable case tabs, set the `enableTabManagement` feature toggle to `true` in your front-end implementation. For more information on this feature toggle, visit [this page](../../nog-een-plek-geven/reference/feature-toggles.md).

## Case tabs types

Valtimo supports the following 3 different types of case tabs.

<table><thead><tr><th width="191">Type</th><th width="180">Type key</th><th>Description</th></tr></thead><tbody><tr><td><strong>Standard</strong></td><td>standard</td><td>A collection of tabs is available that support different Valtimo features. These range from showing a summary form, or showing an audit log to showing the current state of the BPMN process. The tabs that are available are listed below.</td></tr><tr><td><strong>Form.io</strong></td><td>formio</td><td>Form.io tabs can be configured to show a Form.io form as the tab content. It is purely meant to display information, as there is no way to submit the information even if a submit button has been added to the form definition.</td></tr><tr><td><strong>Custom</strong></td><td>custom</td><td>Custom tabs can be configured to show a custom Angular component.</td></tr></tbody></table>

### Standard tabs&#x20;

Valtimo comes with a number of tabs that support different features.&#x20;

<table><thead><tr><th width="192">Type</th><th width="180">Type key</th><th>Description</th></tr></thead><tbody><tr><td><strong>Summary</strong></td><td>summary</td><td>Shows a single Form.io form with the name: '.summary'.</td></tr><tr><td><strong>Progress</strong></td><td>progress</td><td>Shows a BPMN model with the progress of the case.</td></tr><tr><td><strong>Audit</strong></td><td>audit</td><td>Shows the audit logging for the case.</td></tr><tr><td><strong>Documents</strong></td><td>documents</td><td>Shows all files and documents that are associated with the case.</td></tr><tr><td><strong>Contact-moments</strong></td><td>contact-moments</td><td>Shows all contact moments with a client that are registered in the <a href="https://vng-realisatie.github.io/gemma-zaken/standaard/contactmomenten/index">contactmomenten API</a>.</td></tr><tr><td><strong>Zaakobjecten</strong></td><td>zaakobjecten</td><td>Shows all 'zaak' objects of a case.</td></tr><tr><td><strong>Notes</strong></td><td>notes</td><td>Allows case workers to add and read notes for the case.</td></tr></tbody></table>

## Configuring case tabs

By default Valtimo will create a set of standard tabs for each new case definition as displayed below.\
Do not be afraid to delete these standard tabs, by using the **Add tab** button these can easily be replaced.&#x20;

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

The **Add tab** button will open the **Add new tab in \<case>** modal. Here the standard tabs can be found again but it is also possible to select an existing formIO form.\
\
The Custom component button gives access to the available custom components within the Valtimo implementation. Custom components need to be added to the codebase via plugins or implementation  code. Once added to the codebase these will become available in this modal to configure as a tab.\
<mark style="color:red;">Click here for more detailed instructions on how to write custom components.</mark>

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>



{% tabs %}
{% tab title="Via UI" %}
The case tab menu is found under the admin menu. Admin privileges are required to configure case tabs.

1. Go to the Admin menu
2. Go to the 'Cases' menu
3. Click on the case for which tabs need to be configured
4. Click on the 'Add tab' button

<figure><img src="https://docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F3233153254-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Ft4wirndok2gT4h2DRoVf%252Fuploads%252Fgit-blob-07a2ddeff8dc69f6fb08e7a7577b8829bbb85f5e%252Fadd-tab-button.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=1f874fb1&#x26;sv=1" alt=""><figcaption><p>Add tab button</p></figcaption></figure>

5. Select which tab type you want to configure

<figure><img src="https://docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F3233153254-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Ft4wirndok2gT4h2DRoVf%252Fuploads%252Fgit-blob-1c7789ebc71bf4f800ec54302cf603cc99bdb534%252Ftab-select-modal.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=19c94c10&#x26;sv=1" alt=""><figcaption><p>Example of selecting a tab type</p></figcaption></figure>

6. Fill in the form. If no name is set, then the key will be used for translation (in your translation files, add the key under 'dossier.tabs.{YOUR\_TAB\_KEY}')

<figure><img src="https://docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F3233153254-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Ft4wirndok2gT4h2DRoVf%252Fuploads%252Fgit-blob-ca5b3e6934163f2d90983e35e429b30d6b12fa3a%252Ftab-config-modal.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=82f3d2f5&#x26;sv=1" alt=""><figcaption><p>Example of configuring a tab</p></figcaption></figure>

7. Click the button 'Add tab'

If there are no tabs to be configured for one specific type, then the button in the Step 5 modal will be disabled.

<figure><img src="https://docs.valtimo.nl/~gitbook/image?url=https%3A%2F%2F3233153254-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Ft4wirndok2gT4h2DRoVf%252Fuploads%252Fgit-blob-5c52350d2b5040ea28602c436c60a1fc32f8a9f5%252Ftab-select-disabled.png%3Falt%3Dmedia&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=dafe18e6&#x26;sv=1" alt=""><figcaption><p>Example of disabled tab type</p></figcaption></figure>

This can occur for one of two reasons:

* You have already configured all possible tabs of a type
* There are no tabs provided for configuration (i.e. no form definitions or no configurations for custom tabs)
{% endtab %}

{% tab title="Via IDE" %}
Case tabs can be auto-deployed from a JSON file at startup. This is useful to keep the case tab configuration identical across multiple environments. Case tabs are auto-deployed by scanning files on the classpath that end in `.case-tabs.json`.

#### Changesets <a href="#changesets" id="changesets"></a>

Every deployment file for represents a changeset. These files are required to contain a changesetId that should be unique over all deployment files that use changesets. When starting up, changesets that have already been executed will be ignored. A checksum of the changeset is created when it is executed. Changesets that have already been deployed should not change. Changesets that have been changed since a previous time will result in an error and failure to start the application.

All changesets can be executed again, even when the content has changed, by setting the `valtimo.changelog.case-tabs.clear-tables` property to `true`.

#### Example <a href="#example" id="example"></a>

You can find an example of the JSON below.

In this example a tab is created with type `standard`. Different tab types can be used to customize the tab.&#x20;

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
{% endtab %}
{% endtabs %}
