# Using the OpenZaak Plugin

The OpenZaak plugin is used to provide authentication for ZGW (Zaakgericht Werken) plugins that connect to APIs which 
are supported in openzaak. Currently the plugin that this plugin can provide authentication for are the following:

- [Documenten API](../documenten-api/configure-plugin.md)
- [Zaken API](../zaken-api/configure-plugin.md)

### Prerequisites

This page requires knowledge on how to configure OpenZaak

## Configuring the plugin

A plugin configuration is required before the plugin can be used. A general description on how to configure
plugins can be found [here](../configure-plugin.md).

If the OpenZaak plugin is not visible in the plugin menu, it is possible the application is missing a dependency.
Instructions on how to add the OpenZaak dependency can be found 
[here](/valtimo-implementation/modules/openzaak.md).

To configure this plugin the following properties have to be entered:
- **Client ID** The client ID as configured for the 'applicatie' in OpenZaak
- **Secret** The secret as configured for the 'applicatie' in OpenZaak

An example plugin configuration:
![example plugin configuration](img/configure-plugin.png)