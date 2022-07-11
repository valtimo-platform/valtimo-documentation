# Creating custom plugin definitions

## Creating a plugin definition

### Creating a plugin class

A plugin can be created with the `@Plugin` annotation on the class. All classes with the plugin annotation are
detected when the application is started. The plugin class shouldn't be a Spring bean.

For example:

```kotlin
@Plugin(
    key = "twitter",
    title = "Twitter Plugin",
    description = "Tweet and retweet with this new Twitter plugin"
)
class TwitterPlugin {
    ...
```

### Plugin properties

A plugin can be configured with properties. Properties can be added to the plugin class with the `@PluginProperty`
annotation.

For example:

```kotlin
@PluginProperty(key = "username")
private lateinit var username: String
```

### Plugin action

A plugin class can have methods that are marked as actions through the `@PluginAction` annotation. These methods can
then be used in a process definition through the use of [process links](../../using-valtimo/plugin/create-process-link.md). 
A single action can be linked to a task, and will run when that task is reached.

For example:

```kotlin
@PluginAction(
    key = "post-tweet",
    title = "Post tweet",
    description = "Post a tweet on twitter.",
    activityTypes = [ActivityType.SERVICE_TASK]
)
fun postTweet(execution: DelegateExecution, postTweetProperties: PostTweetProperties) {
    ...
```

## Creating a plugin factory

The newly created plugin class can not be used yet because Valtimo does not know how to create the new plugin. This
problem is solved by creating a factory that extends the `PluginFactory` and registering it as a bean. 
The `create()` method has to be implemented to inject Spring beans or other objects that are necessary. This does not
include plugin properties, those are set automatically.

For example:

```kotlin
@Component
class TwitterPluginFactory(
    private val twitterClient: TwitterClient
) : PluginFactory<TwitterPlugin>() {

    override fun create(): TwitterPlugin {
        return TwitterPlugin(twitterClient)
    }
}
```
