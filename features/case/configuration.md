# Configuration

Case specific configurations can be made that have effect on the behaviour of active cases and the processes that support these cases.

Currently the only option is to define if the case can have a case handler assigned to the case.\
Once selected, a second option will appear that configures if all user tasks in the processes that support the case should automatically be assigned to the case handler.

{% tabs %}
{% tab title="Via UI" %}
<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption><p>Case specific configuration</p></figcaption></figure>
{% endtab %}

{% tab title="Via IDE" %}
Case settings can be loaded automatically when creating a case by reading a configuration file. **This file will only be used when creating a case definition to avoid overriding user configuration.**

A file should be created on the classpath in the `/config/case/definition` folder. The filename should be the name of the document definition and use the `json` file extension. So if there is a document definition with the name `loans` then the json file should be named `loans.json`

```json
{
    "canHaveAssignee": true,
    "autoAssignTasks": true
}
```

`autoAssignTasks` can only be set to true when `canHaveAssignee` is true.

Any value not present in the json file will not be loaded and will instead use the default value (`false`). Auto-deployed case configuration settings are validated against unsupported properties or invalid values.
{% endtab %}
{% endtabs %}
