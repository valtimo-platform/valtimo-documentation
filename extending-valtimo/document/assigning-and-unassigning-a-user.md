# Assigning and unassigning a user

A document definition is a JSON document that defines the structure that document has, as well as restrict
the allowed values for each property through validation rules. This page shows how to assign and unassign 
users to and from a case.

## Assigning a user

There are two methods available to assign a user:

1) Using the endpoint `POST /api/document/{documentId}/assign` and providing a user id in the request body.
  ```json
  {
    "assigneeId" : "some UUID"
  } 
  ```
2) Using an expression inside a process and providing the email address of the user
  ```
  ${documentDelegate.setAssignee(execution, "assignee email address")}
  ```

## Unassigning a user

When a user is assigned to a document there is an endpoint to unassign a user 
`POST /api/document/{documentId}/unassign`

There is no need to provide a user id to this endpoint.
