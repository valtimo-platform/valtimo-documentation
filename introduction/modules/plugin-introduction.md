# What are plugins

Plugins are extensions on the Valtimo platform, allowing connections to other services, whether external or internal. 
Some plugins are provided by the platform, but developers can create their own as well.

Plugins consist of several parts; the definition itself, dictating both the properties that can be configured
and the actions the plugin can run. The concepts are all explained below.

## Concepts

* **Plugin definition.** A regular plugin is often referred to as a plugin definition to emphasize the difference 
between the definition of the plugin and the configuration of a plugin. For example, a Twitter plugin can also be
referred to as a Twitter plugin definition.

* **Plugin configuration.** A single plugin can be configured multiple times. For example, a Twitter plugin might have 
one configuration to post tweets for one user and another configuration to post tweets for another user.

* **Plugin property.** A plugin configuration can have multiple configurable properties. For example, a Twitter 
plugin configuration can have the properties `username` and `password`.

* **Plugin action.** A plugin can have several actions it can execute. For example, a Twitter plugin might have 
one action to post a tweet and another action to like a tweet.

* **Plugin event.** A plugin might have methods that need to be run when the Plugin is created, updated or deleted. 
For example, a plugin might need approval from an external service for its instantiation.

* **Plugin action property.** An action can have several properties that can be configured differently, depending on
the process instance or process definition. For example, a Twitter plugin action which posts a tweet would include both
the user and the message.

In order to use an existing plugin, a plugin configuration needs to be added. This can be found 
[here](../../using-valtimo/plugin/configure-plugin.md).
