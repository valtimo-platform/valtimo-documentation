# Auto-deployment for access control
This section describes how permissions can be configured in the backend.

## Auto-deployment
PBAC can be configured in the backend using auto-deployment. This is useful when you want to keep permissions identical over multiple environments.
The deployment will scan for files on the classpath matching either `**/*.role.json` or `**/*.permission.json` for respectively role- and permission configurations.

Every deployment file for PBAC represents a changeset, much like Liquibase. 
These files contain a `changesetId` that should be unique over all deployment files that use changesets (currently only the Authorization module).

The contents of a changeset cannot change as long as the `changesetId` does not. A change to an existing changeset can only be made when the `changesetId` also changes.
Changes made to the deployment files of PBAC will result in a full recreation of existing role- or permission configuration.

## Configuring roles
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

## Configuring permissions
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
                    "clazz": "int"
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
### Joining entities using a container
The example below shows how container conditions can be used to join other entities.
In this case, the permission is defined:
- A user with `ROLE_USER` can `VIEW` notes where
  - the related document-definition name equals `loans`
  - the related document is assigned to the current user

`note.permission.json`:
``` json
{
    "changesetId": "pbac-notes",
    "permissions": [
        {
            "resourceType": "com.ritense.note.domain.Note",
            "action": "view",
            "roleKey": "ROLE_USER",
            "conditions": [
                {
                    "type": "container",
                    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocument",
                    "conditions": [
                        {
                            "type": "field",
                            "field": "documentDefinitionId.name",
                            "operator": "==",
                            "value": "loans"
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
    ]
}
```

