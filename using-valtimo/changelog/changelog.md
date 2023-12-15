# Changelog - a generic framework for autodeployment

## Context
Implementing a business process requires a lot of different types of configuration. 
Most of these configurations can be done through the admin interface, such as creating processes, forms and configuring the case list.
Often however, it is recommended to use configuration files:  
- By adding the configuration files to the Valtimo backend sourcecode, it is guaranteed that the configuration is deployed to every environment. 
- The risk of manual errors is decreased
- The configuration files are part of a version control system, e.g. Git.

Historically, Valtimo supports different autodeployment strategies for different types of configuration. 
Introduced in Valtimo 10.7, the changelog module aims to provide one generic autodeployment strategy.

## Definitions
### Deployment file
A file that is part of the Valtimo backend implementation sourcecode, containing a specific type of configuration. 
Deployment files are scanned based on the extension of the file. E.g.:  
- all.role.json
- task.permission.json
- all.dashboard.json

### Changeset
Every deployment file represents a changeset. A changeset contains a `changesetId` that should be unique over all deployment files that use changesets.
The contents of a changeset cannot change as long as the changesetId does not change as well. 
A change to an existing changeset can only be made when the changesetId also changes.