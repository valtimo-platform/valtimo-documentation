# Backend-end access control
This section describes how Policy Based Access Control (PBAC) can be configured in the backend.

## Autodeployment
PBAC can be configured in the backend using auto-deployment. 
The deployment will scan for files on the classpath matching either `**/*.role.json` or `**/*.permission.json` for respectively role- and permission configurations.

Every deployment file for PBAC represents a changeset, much like Liquibase. 
These files contain a `changesetId` that should be unique over all deployment files that use changesets (currently only PBAC).

The contents of a changeset cannot change as long as the `changesetId` does not. A change to an existing changeset can only be made when the `changesetId` also changes.
Changes made to the deployment files of PBAC will result in a full recreation of existing role- or permission configuration.

## Configuring roles
The roles should be defined before permissions can be deployed. The file contains only a list of role names next to the mandatory `changesetId`.
Roles names should match the roles in Keycloak (or Active Directory, depending on the configuration).

`all.role.json`:
``` json
{
    "changesetId": "pbac-roles-v1",
    "roles": [
        "ROLE_USER",
        "ROLE_ADMIN"
    ]
}
```


## Configuring permissions
Permissions are a bit more complex than the roles.
> **TODO: Add a detailed explanation of the contents of a permission**

`document.permission.json`:
``` json
{
    "changesetId": "pbac-documents-v1",
    "permissions": [
        {
            "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
            "action": "view",
            "roleKey": "ROLE_ADMIN"
        },
        {
            "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
            "action": "list_view",
            "roleKey": "ROLE_USER",
            "conditionContainer": {
                "conditions": [
                    {
                        "type": "expression",
                        "field": "content.content",
                        "path": "$.height",
                        "operator": "<",
                        "value": 20000,
                        "clazz": "int"
                    },
                    {
                        "type": "field",
                        "field": "documentDefinitionId.name",
                        "operator": "==",
                        "value": "leningen"
                    }
                ]
            }
        }
    ]
}
```

`note.permission.json`:
``` json
{
    "changesetId": "pbac-note-v1",
    "permissions": [
        {
            "resourceType": "com.ritense.note.domain.Note",
            "action": "view",
            "roleKey": "ROLE_USER",
            "conditionContainer": {
                "conditions": [
                    {
                        "type": "container",
                        "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
                        "conditions": [
                            {
                                "type": "field",
                                "field": "documentDefinitionId.name",
                                "operator": "==",
                                "value": "leningen"
                            },
                            {
                                "type": "field",
                                "field": "assigneeId",
                                "operator": "==",
                                "value": "${currentUserId}"
                            }
                        ]
                    }
                ]
            }
        }
    ]
}
```

