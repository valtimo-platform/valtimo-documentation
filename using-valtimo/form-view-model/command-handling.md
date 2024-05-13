# Command handling

A command is used to change the state of an application. Commands allow you to express clear intentions which simplify understanding and debugging of the application.

In this module, commands are used to handle form submissions. The command handling process is divided into two parts: the command itself and the command handler.

## Command
A command is a data class that represents the intention to change the state of the application. It should be a data class that implements the `Command` interface.

Here is an example of a command:
```kotlin
data class ExampleCommand(
    val age: Int
) : Command<Unit> {

    init {
        if (age > 18) {
            println("You are an adult")
        } else {
            throw FormException("You are not an adult", component = "age")
        }
    }
}
```

## Command handler
The command handler is a class that is used to handle the command. It should implement the `CommandHandler` interface.

The `execute()` method is used to execute the command.

The command handler also needs to be registered as a bean in the Spring context.

Here is an example of a command handler:
```kotlin
@Component
class ExampleCommandHandler : CommandHandler<ExampleCommand, Unit> {

    override fun execute(command: ExampleCommand) {
        // ... handle the command ie: save to database or call another service
    }
}
```
