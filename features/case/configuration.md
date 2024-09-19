# Configuration

Case specific configurations can be made that have effect on the behaviour of active cases and the processes that support these cases.

Currently there are two options that can be configured on this page.

* Configure if the case can have a case handler assigned.
* Configure if user tasks are automatically assigned to the case handler.

Once the case handler option is selected, the second checkbox will appear that configures if all user tasks in the processes that support the case should automatically be assigned to the case handler.

{% tabs %}
{% tab title="Via UI" %}
<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption><p>Case specific configuration</p></figcaption></figure>

When the case handler option is selected the following changes in the user interface:

*   **The case list screen is divided in to three tabs**\


    <figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption><p>Case overview with case handler option selected<br></p></figcaption></figure>

    * **All cases**\
      _This overview is the same as for cases that do not have a case handler configured._\
      _All cases are displayed on this tab._
    * **My cases**\
      _Overview of cases that are assigned to the user that is currently logged in._
    * **Unassigned cases**\
      _Overview of cases that are not assigned to a case handler_\

* **An "Assignee" column is automatically added to the case list columns**\
  This column displays the case handler assigned to each case in the overview. This column is fixed and can't be removed via the case list configuration page.\

*   **An option to assign a case handler on the case details page.**\
    When clicked a dropdown menu is displayed with all case handlers that can be assigned to the case. Case handlers can be configured via [Access control](../access-control/) for each case type.\


    <figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption><p>Select case handler option</p></figcaption></figure>

    \
    An additional menu is added to the header of the case making it possible to immediately "claim" the case by the logged in user. The unassign option removes the case handler that is currently assigned to the case. Who is allowed to claim, assign and unassign is all configured via [Access control](../access-control/).\


    <figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption><p>Menu to claim a case or unassign the current assignee</p></figcaption></figure>
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
