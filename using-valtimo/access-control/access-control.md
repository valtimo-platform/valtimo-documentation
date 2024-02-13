# Access control

Valtimo supports Policy Based Access Control (PBAC) as an authorization layer via this module.
This layer allows you to restrict access to functionality or data based on policies.

## Roles
A role is an entity where permissions can be linked to. The role names should match the roles in the JWT token by OpenId/OAuth2 (Keycloak).

## Permissions
Permissions define whether a user with a specific role can access or act on the configured resource.

Multiple permissions are evaluated as `OR`:
The outcome of an authorization request is `true` when **any** of the permissions passes **all** the configured checks.
When permissions are used to filter data from a list query, the result will contain every entry that passes the checks of **any** permission.

When selecting applicable permissions for evaluation, the following checks are performed:
- The user has the role that is configured for the permission
- The requested resource matches the permission's resource
- The required action matches the permission's action 

## Conditions
Extra conditions can be applied to a permission to tighten the access to resources. These conditions are optional.
Conditions are evaluated as `AND`, which means the **all** configured conditions on a permission should evaluate to `true` to pass the permission checks.

Conditions can also be nested by using a container. This allows you to join another resource to the root resource, on which you can add conditions as well.
An example of this can be found [here](auto-deployment-access-control.md#joining-entities-using-a-container)

## When is access control applied?

Access control is always applied by default. This means that when a user requests a resource, the access control layer 
will check if the user has the required permissions to access the resource. To prevent certain actions from being checked 
by the access control layer, this needs to be explicitly configured. Tasks and listeners used in BPMN models are not 
considered being accessed by a user, and therefore do not have access control applied to them.

To prevent access control from being applied when writing custom code, `runWithoutAuthorization` can be used. See [the
extending valtimo page](/extending-valtimo/access-control/run-without-access-control.md) for more information.


## Configuration
The following sections contains information on how to configure and use access control.
* [Auto-deployment access control](auto-deployment-access-control.md)
* [Applying access control in front-end](frontend-access-control.md)
* [Configuring roles](configuring-roles.md)
* [Configuring permissions](configuring-permissions.md)
