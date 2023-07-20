# Access control

Valtimo supports Policy Based Access Control (PBAC) as an authorization layer via this module.
This layer allows you to restrict access to functionality or data based on policies.

## The model


### Roles
A role is a simple entity where permissions can be linked to. The role names should match the roles in the JWT token by OpenId/OAuth2 (Keycloak).

### Permissions
Permissions are quite a bit more complex than the roles.

Multiple permissions are evaluated as OR:
The outcome of a permission (action) check is true when ANY of the permissions passes its checks.
When permissions are used to filter data from a list query, the result will contain every entry that passes the checks of ANY permission.

When selecting applicable permissions for evaluation, the following checks are performed:
- The user has the role that is configured for the permission
- The requested resource matches the permissions' resource
- The required action matches the permissions' action 

### Conditions
Extra conditions can be applied to a permission to tighten the access to resources. These conditions are optional.
Conditions are evaluated as AND, which means the ALL configured conditions on a permission should evaluate to true to pass the permission checks.

Conditions can also be nested by using a container. This allows you to join another resource to the root resource, on which you can add conditions as well.

## Configuration
The following sections contains information on how to configure and use access control.
* [Back-end access control](backend-access-control.md)
* [Front-end access control](frontend-access-control.md)
