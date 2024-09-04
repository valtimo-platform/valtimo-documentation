# Logging

What is logging and why do I want to use it

## Log levels and when to use them

There are several log levels available, each with their own use cases. Different log levels
are used to indicate the severity of the message. The log levels are listed below in order of
most severe to least severe, with examples of when to use them.

### ERROR
* Runtime errors or (other) unexpected, blocking conditions.

### WARN
* First time use of deprecated APIs after startup.
* Unexpected behavior for the consumer of the API that may or may not have impact.
  * E.g: Importing a case definition, and some configuration already exists in the database.

### INFO
*  Interaction with external systems that goes beyond retrieving data.
  * Sending an email.
  * Setting a status.
* Significant and noteworthy business events.
  * Starting/Finishing deployments of configuration.
  * Completing a task.
  * Creating a case.
  * Creating a form flow. 
  * Important setup steps at startup of application.
* Creating important configuration.
  * Document definitions. 
  * Process definitions. 
  * Form definitions.
  * Plugin configuration.

### DEBUG
* Interaction with external systems to retrieve data.
* For tracking the flow of the application.
  * E.g. checking permissions of a user for a certain resource and action.
* State changes to resources.
* Responses from calls to external systems.

### TRACE
* Parameters of method calls for low level troubleshooting.

## The `@LoggableResource` annotation
By default, Valtimo ships with the `@LoggableResource` annotation. This annotation is used
to provide additional information for any log messages that are created by the application.
The annotation can be used on any argument of a method, as long as the class is managed
by Spring. The annotation is used as such:

```kotlin
@Component
class SomeSpringManagedClass() {
    fun someMethod(
        resource: LogResource,
        @LoggableResource(resourceType = String::class) taskId: String,
    ) {
        resource.logSomething()
    }
}
```

In the example above, `@LoggableResource` defines what resource type the `taskId` belongs
to. This information is then used to provide additional context in the log message, by
storing it in this variable.

