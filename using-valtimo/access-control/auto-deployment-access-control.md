# Auto-deployment for access control
This section describes how permissions can be configured in the backend.

## Auto-deployment
PBAC can be configured in the backend using auto-deployment. The autodeployment of PBAC configuration is based on the [changlog framework](/using-valtimo/changelog/changelog.md).
The changelog framework will scan for files on the classpath matching either `**/*.role.json` or `**/*.permission.json` for respectively role- and permission configurations.

### Configuring roles
The roles should be defined before permissions can be deployed. The file contains only a list of role names next to the mandatory `changesetId`.

`all.role.json`:
``` json
{
    "changesetId": "pbac-roles",
    "roles": [
        "ROLE_USER",
        "ROLE_ADMIN"
    ]
}
```

### Configuring permissions
The example below defines 2 permissions:
- A user with `ROLE_ADMIN` can `VIEW` any document
- A user with `ROLE_USER` can `VIEW` documents where:
  - the name of the document-definition equals `loans`
  - the `height` of the loan is less than 20000

`document.permission.json`:
``` json
{
    "changesetId": "pbac-documents",
    "permissions": [
        {
            "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
            "action": "view",
            "roleKey": "ROLE_ADMIN"
        },
        {
            "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
            "action": "view_list",
            "roleKey": "ROLE_USER",
            "conditions": [
                {
                    "type": "expression",
                    "field": "content.content",
                    "path": "$.height",
                    "operator": "<",
                    "value": 20000,
                    "clazz": "java.lang.Integer"
                },
                {
                    "type": "field",
                    "field": "documentDefinitionId.name",
                    "operator": "==",
                    "value": "loans"
                }
            ]
        }
    ]
}
```

### Clear tables
PBAC configuration that has been added using autodeployment can conflict with manual changes that have been done through the admin interface.
A way to resolve this conflict is by setting the `valtimo.changelog.pbac.clear-tables` Spring property to `true`. 
If 'clear tables' is enabled, all roles and permissions in the database will be cleared when Valtimo starts, and the configuration in the autodeployment files will be deployed.

### Examples
More examples of PBAC configuration can be found in the [valtimo-examples repository](https://github.com/valtimo-platform/valtimo-examples).