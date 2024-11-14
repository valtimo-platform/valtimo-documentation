# Assigning and unassigning a user

Cases can have a user assigned to them. This allows for user to see if a particular case is already in progress.

This page shows how a user can be assigned and unassigned to and from a case using code.

## Assigning a user

There are two methods available to assign a user:

1. Using the endpoint `POST /api/document/{documentId}/assign` and providing a user id in the request body.

```json
{
  "assigneeId": "some UUID"
} 
```

2. Using an expression inside a process and providing the email address of the user

```spel
${documentDelegate.setAssignee(execution, "assignee email address")}
```

## Unassigning a user

There are two methods available to remove the assigned user from a case:

1. Using the endpoint `POST /api/document/{documentId}/unassign`.
2. Using an expression inside a process:

```spel
${documentDelegate.unassign(execution)}
```

## Related

[Assigning a user](assigning-a-user.md)
