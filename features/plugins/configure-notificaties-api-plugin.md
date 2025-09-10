# Notificaties API plugin

{% hint style="success" %}
The Notificaties API plugin is a ZGW plugin and can only be used in the GZAC edition.
{% endhint %}

The Notificaties API plugin is used

### Prerequisites

This page requires knowledge on how to configure the Notificaties API

## Configuring the plugin

A plugin configuration is required before the plugin can be used. A general description on how to configure plugins can be found [here](broken-reference).

If the Notificaties API plugin is not visible in the plugin menu, it is possible the application is missing a dependency. Instructions on how to add the Notificaties API dependency can be found [here](broken-reference).

To configure this plugin the following properties have to be entered (in addition to the optional Configuration ID and required Configuration name):

* **Notificaties API URL (`url`).** Contains the complete base URL of the Notificaties API to connect to. This generally includes the path `/api/v1/`.
* **Callback URL (`callbackUrl`).** Contains the complete callback url of Valtimo the Notificaties API will send updates on subscriptions to.
* **Authentication plugin configuration (`authenticationPluginConfiguration`).** Reference to another plugin configuration that will be used to add authentication to any request performed on the Notificaties API. If no option is available in this field a plugin has to be configured that is able to authenticate for the specific application that hosts the Notificaties API.

An example plugin configuration:&#x20;

<figure><img src="../../.gitbook/assets/configure-plugin-notificaties.png" alt=""><figcaption></figcaption></figure>

## Subscriptions

When working with the Notificaties API, it is important to keep subscriptions (abonnementen) as specific as possible.
Otherwise, the Notificaties API will send more messages than Valtimo is interested in, leading to more stress on both
systems.

The number of subscriptions is kept to a minimum by evaluating plugin configurations that depend on the Notificaties
API, such as the Portaaltaak plugin and the Verzoek plugin. As a result, all channels that are subscribed to are combined
into a single subscription.
