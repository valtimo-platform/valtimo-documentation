# Configuring permissions
In order to allow users to perform certain actions, permissions have to be set up for a specific role. For information
on how to configure roles, see [this page](configuring-roles.md).

## How to create permissions
Creating permissions is done for a specific role. Assuming a role is present, clicking on that role in the
`Access control` interface will allow permissions to be configured.

![configuring-permissions-example](img/configuring-permissions.png)

The image above shows all the permissions that have been configured for `ROLE_USER`. Here, permissions can be added,
edited and removed. Since the list shown here is the full list of permissions for this role, removing a permission from
the list and saving it will also result in the removal of that permission in Valtimo. 

### Permission structure
There are a lot of elements that can be specified for permissions. As an example, someone with `ROLE_USER` can have
access to cases of type `example-document-definition`, or if that someone has been assigned to the case. The following
two permissions are used to define this:

```json
[
    {
        "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
        "action": "view_list",
        "conditions": [
            {
                "type": "field",
                "field": "documentDefinitionId.name",
                "operator": "==",
                "value": "example-document-definition"
            }
        ]
    },
    {
        "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
        "action": "view_list",
        "conditions": [
            {
                "type": "field",
                "field": "assigneeId",
                "operator": "==",
                "value": "${currentUserId}"
            }
        ]
    }
]
```

Going over each element:
* `resourceType` is required to specify what resource type this permission applies to. For information on the resource
  types Valtimo provides out of the box, see [here](/reference/modules/authorization.md). For information on how to register custom resource types, see
  [here](/extending-valtimo/access-control/registering-a-resource.md).
* `actionKey` specifies the kind of action that is being done. In this case, viewing a list. For a list of actions, see
  [here](/reference/modules/authorization.md).
* `conditions` is a list describing all the conditions that apply to this particular permission. This requires
  knowledge of the code for the resource type, as fields can be specified in here correspond to fields inside the class.
  For information on the kinds of conditions that can be specified, as well as the fields, see [this page](/reference/modules/authorization.md#supported-conditions).
  Permission is only granted when all conditions for that permission are met.

### Exporting permissions
Exporting permissions for a specific role can be done here, or on the [list in bulk](configuring-roles.md#export). When
exporting permissions from the permission configuration page, be sure to save the configurations first if any edits have
been made. Exporting will add a few more fields that are not necessary when configuring permissions via the UI, but are
necessary when doing auto-deployment. For information on auto-deployment, see [this page](auto-deployment-access-control.md#auto-deployment).

![exporting-permissions-example](img/exporting-permissions.png)

### Deleting permissions
Deleting permissions will also delete the accompanying role. Deleting roles will not delete the role in Keycloak.

![deleting-permissions-example](img/deleting-permissions.png)