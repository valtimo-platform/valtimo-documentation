# Logging

Events are logged in order to be able to track what happened in an application. This is useful for example when
trying to debug an issue. Valtimo uses Logback as the logging framework. The documentation for this framework can be
found [here](https://logback.qos.ch/documentation.html).

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
*  Mutating data in external systems
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
* Reading data from external systems
* For tracking the flow of the application.
  * E.g. checking permissions of a user for a certain resource and action.
* State changes to resources.
* Responses from calls to external systems.

### TRACE
* Parameters of method calls for low level troubleshooting.

## Providing context to log messages

When logging messages, it is important to know which resources were being interacted with. There are three ways to
provide context to log messages:

### The `@LoggableResource` annotation
By default, Valtimo ships with the `@LoggableResource` annotation. This annotation is used
to provide additional information for any log messages that are created by the application.
The annotation can be used on any one argument of a method, as long as the class is managed
by Spring. The annotation is used as such:

```kotlin
@Component
class SomeSpringManagedClass(...) {
    fun someMethod(
        @LoggableResource(resourceType = Task::class) taskId: String,
    ) {
        // What you want the method to do goes here
    }
}
```

In the example above, `@LoggableResource` defines what resource type the `taskId` belongs
to. We specify the `Task` class because that is what the `taskId` refers to.
This information is then used to provide additional context in the log message, by storing it in this variable.

### The `withLoggingContext()` function
In situations where the `@LoggableResource` annotation cannot be used, the `withLoggingContext()` function can be used
instead. Examples of when to use this function include:
* When the class is not managed by Spring.
* When the resource is not yet known at the time of the method call.

The `withLoggingContext()` function is used as such:

```kotlin
class SomeClass(...) {
    fun someMethod(taskId: String) {
        withLoggingContext(Task::class.java.canonicalName to taskId) {
            // What you want the method to do goes here
        }
    }
}
```

This accomplishes the same as the LoggableResource annotation, but does not depend on Spring. This can of course also be
used to provide additional context are not necessarily related to resources.

### Directly working with MDC

Rather than using with `@LoggableResource` or `withLoggingContext()`, you can also directly work with the MDC.
The MDC (Mapped Diagnostic Context) is a map that is used to store additional context information for log messages.
This is used by `withLoggingContext()` as well, but can be used directly if needed. This is done via the MDC class in
this manner:

```kotlin
class SomeClass(...) {
    fun someMethod(taskId: String) {
        MDC.put(Task::class.java.canonicalName, taskId)
        // What you want the method to do goes here
        MDC.remove(Task::class.java.canonicalName)
    }
}
```

This accomplishes the same as the LoggableResource annotation and the `withLoggingContext` mehod, but does not depend on
Spring. This can of course also be used to provide additional context are not necessarily related to resources.

### Logging when class is not available 

#### Internal class reference not accessible

When an internal class reference is not available inside application code, specify this class reference as a string:

```kotlin
@Component
class SomeSpringManagedClass(...) {
    fun someMethod(
      @LoggableResource(resourceTypeName = "com.ritense.document.domain.impl.JsonSchemaDocument") documentId: String,
    ) {
        // What you want the method to do goes here
    }
}
```

#### External resource

When an external resource is not available inside application code, refer to a string resource type name, 
preferable stored in a constants object to make it reusable:

```kotlin
@Component
class SomeSpringManagedClass(...) {
    fun someMethod(
      // Documenten API: enkelvoudig informatieobject
      @LoggableResource(resourceTypeName = DOCUMENTEN_API.ENKELVOUDIG_INFORMATIE_OBJECT) documentUrl: String,
    ) {
        // What you want the method to do goes here
    }
}
```
