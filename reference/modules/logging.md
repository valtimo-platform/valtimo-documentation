# Logging

## Log levels and when to use them

### ERROR

* Runtime errors or other unexpected conditions

### WARN

* First time use of deprecated APIs after startup.
* Unexpected behavior for the consumer of the API that may or may not have impact.
  * E.g: Importing a case definition, and some configuration already exists in the database

### INFO

*  Interaction with external systems that goes beyond retrieving data
  * sending an email
  * setting a status
* Significant and noteworthy business events.
  * Starting/Finishing deployments of configuration 
  * Completing a task 
  * Creating a case 
  * Creating a form flow 
  * Important setup steps at startup of application
* Creating important configuration
  * Document definitions 
  * Process definitions 
  * Form definitions 
  * Plugin configuration

### DEBUG

* Interaction with external systems to retrieve data
* For tracking the flow of the application
  * E.g. checking permissions of a user for a certain resource and action
* State changes to resources
* Responses from calls to external systems

### TRACE

* Parameters of method calls for low level troubleshooting
