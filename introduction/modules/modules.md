# Available modules

## Core

### Audit

Audit provides a framework to record and store actions performed by users. Certain actions in the other modules of
Valtimo, like completing a task or uploading a file will be audited by default. It is possible to audit other actions
by using this feature in the implementation code. The audit trail is available by case to show the history of
actions for that case.

### Besluit

Besluit contains a connector used to connect to the Besluiten API, a Dutch government API standard for exchanging
information around besluiten. It allows the creation of besluiten and their relation to documents from processes.

### Connector

Connectors are Valtimo configurable components that can be used to connect to external systems. This module provides a
framework to create, configure, and use connectors. Certain Valtimo modules include their own connectors that will be
automatically available for configuration when starting a Valtimo instance.

### Contactmoment

The Contactmomenten API is a Dutch government API standard for storage of and access to contactmomenten. A connector is
provided that can be used to access the Contactmomenten API. This allows for the creation of contactmomenten. Any mail
sent by Valtimo will be registered in this API.

### Contract

Contract contains certain interfaces and events that Valtimo uses in several other modules. Apart from this, contract
sanitizes endpoint output when exceptions occur. A liquibase runner is available that allows other modules to define
liquibase configuration that is run on startup. Finally, contract include several helper classes, like the
`QueryDialectHelper` bean that can be used in criteria queries to add JSON column clauses to the query.

### Core

Core contains and builds upon the Camunda process engine that enables Valtimo to run processes. Several endpoint and
functions are available that provide Task and Process data. It also includes choice fields. A generic way to create
lists of values, that can be used by the application. Some security features used to control access to any Valtimo
endpoints are also part of this module.

### Documents

A document is the starting point of the case and the main data storage for that case. One or more processes can be
linked to a case, which allows for the document to be created when the case is started.
The content of the document is defined in a document definition, in JSON schema.
Users interact with the document via user tasks; document data can be loaded into task forms, and user input can be
stored in the document after completing a task.

### Document generation

Document generation provides an interface for generating documents that can be used within Valtimo. An implementation
needs to be provided by another module, or the application that this is used in.

### Form

Form allows the use of Form.IO forms in Valtimo. Forms can be managed by using the provided endpoints, or loaded from
a configuration file at application startup. These forms can be used by other modules to complete tasks for example.

### Form flow

Form flow allows users to create a sequence of forms, similar to a flow chart or form wizard. A form flow definition
contains the configuration for each step, what the subsequent steps are, and the conditions under which they can be
reached.

### Local document generation

The local document generation module is a stub implementation of the document generation module. It is used as a local
test implementation that allows the application to start without having to call external services when generating a
document. This does *not* generate an actual document, but writes the calls to the application log instead.

### Milestones

The milestones module offers a framework to keep track of how a process is progressing. Milestones can be created
in the admin interface, and can be linked to specific tasks of a process. When that task is completed,
the corresponding milestone is reached.

### Plugins

Plugins are extensions on the Valtimo platform. These are often connections to external
services, such as transactional email and  generating documents. Some plugins are provided
by the platform, but developers can create their own plugins as well. Plugins can be 
configured without writing code, and can be used during BPMN processes. A more in-depth
description can be found [here](plugin-introduction.md).

### Process document

Process document facilitates the link between documents and processes. In order to use a process
with a document, the process needs to be linked to a document. Process document also allows access of document data
from inside a process.

### Resource

Resource is a module that describes how resources can be uploaded and downloaded. This implemented by other modules,
e.g. [OpenZaak resource](#openzaak-resource).

### Temporary resource storage

Temporary resource storage provides a service for storing files locally, e.g. to process it during following tasks.
These files are removed after a preconfigured time.

### Value resolvers

Value resolvers provides a framework for creating custom value resolvers, which can be used inside of
forms to retrieve data from a custom location.

### Web

Web offers web related configuration, such as integration with [Swagger](https://swagger.io/) (to provide 
REST API documentation) and hardening (for strengthening endpoints against outside attacks).

## ZGW (Zaakgericht Werken)

### Catalogi API

The Catalogi (Catalogues) API is a Dutch government API standard for defining the types of zaken and documenten that can 
be used in the Documenten API and Zaken API. A plugin is provided that allows for connecting to applications that 
provide a Catalogi API.

### Documenten API

The Documenten (Documents) API is a Dutch government API standard for storage of and access to documents and their 
metadata. A plugin is provided that allows for connecting to applications that provide a Documenten API.

### Objecten API

The Objecten (Objects) API is a Dutch government API standard for storage of and access to objects and their
metadata. A plugin is provided that allows for connecting to applications that provide an Objecten API.

### Objecten API authentication

The Objecten (Objects) API authentication provides the Object token authentication plugin for authenticating
call to the Objecten API implementation by Maykin Media. This plugin is used by other plugins for the authentication.

### Objecttypen API

The Objecttypen (Objecttypes) API is a Dutch government API standard for storage of and access to object types, without having to
create a new API for each object. A plugin is provided that allows for connecting to applications that provide an 
Objecttypen API.

### OpenZaak

[OpenZaak](https://openzaak.org/) is an application that implements APIs for the exchange of information concerning cases
using the Dutch government API standards for ZGW (Zaakgericht Werken). This module provides a plugin that provides
authentication for other ZGW plugins.

### OpenZaak resource

[OpenZaak](https://openzaak.org/) resource is an implementation of the resource service, providing a way to store
a resource in OpenZaak as an *eenvoudig informatie object* (simple information object).

### SmartDocuments

SmartDocuments itself is an external service that deals with generating documents based on templates and placeholders.
This module offers a plugin which can connect to this service to generate documents.

### Zaken API

The Zaken (Cases) API is a Dutch government API standard for exchanging information around cases and their related data.
A plugin is provided that allows for connecting to applications that provide a Zaken API.
