# Available modules

## Document generation

### SmartDocuments

SmartDocuments itself is an external service that deals with generating documents based on templates and placeholders.
This module offers a plugin which can connect to this service to generate documents.

## OpenZaak

[OpenZaak](https://openzaak.org/) is an application that implements APIs for the exchange of information concerning cases
using the Dutch government API standards for ZGW (Zaakgericht Werken). This module provides a plugin that provides 
authentication for other ZGW plugins.

## Plugins

Plugins are extensions on the Valtimo platform. These are often connections to external
services, such as transactional email and  generating documents. Some plugins are provided
by the platform, but developers can create their own plugins as well. Plugins can be 
configured without writing code, and can be used during BPMN processes. A more in-depth
description can be found [here](plugin-introduction.md).

## ZGW (Zaakgericht Werken)

### Documenten API

The Documenten (Documents) API is a Dutch government API standard meant to standardize the storage of and access to 
documents. A plugin is provided that allows for connecting to applications that provide a Documenten API.

### Zaken API

The Zaken (Cases) API is a Dutch government API standard meant to standardize the information exchange around cases.
A plugin is provided that allows for connecting to applications that provide a Zaken API.
