# Creating custom plugin definitions

## Creating a plugin definition

### Creating a plugin class

A plugin can be created with the `@Plugin` annotation on the class. All classes with the plugin annotation are
detected when the application is started. The plugin class should not be a Spring bean.

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
@PluginProperty(key = "username", secret = false)
private lateinit var username: String
```

By setting the `secret` attribute in this annotation to `true` the plugin property will be marked as a secret. This is
meant to be used for sensitive information (e.g. passwords or API keys). Secrets are encrypted before being stored in
the database and will be automatically decrypted before use in the plugin.

These things should be kept in mind when creating the frontend components for secrets:
- When editing an existing plugin configuration the value will not be sent back to the frontend to avoid exposing
  sensitive data
- Only when submitting a value that is not null or empty string will the property be updated.

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
