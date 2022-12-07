# Process blueprints

Process blueprints are a collection of files, that form a starting point to kickstart an implementation. These often
consist of one or more BPMNs, a document definition, forms, as well as less common things such as custom front-end and
back-end code. These blueprints can be found on GitHub [here](https://github.com/generiekzaakafhandelcomponent/Basisprocessen).

How to create a process blueprint from an existing project can be found [here](TODO).

This page assumes you have the following knowledge:
* How to add dependencies through Gradle/Maven.
* How to use Git.
* How to create and use Spring beans.
* Java/Kotlin knowledge.

## How to import a process blueprint

Importing a process blueprint and customizing it for a specific use case can be done by following the instructions on
this page. Additionally, specific instructions for a blueprint can be found on GitHub for that particular process
blueprint. These always take precedent over these general instructions.

### Copying over the files

This is the general structure of a blueprint:

```
|-- blueprints
|   |-- [name of the blueprint]
|   |   |-- backend
|   |   |   |-- main
|   |   |   |   |-- java
|   |   |   |   |-- kotlin
|   |   |   |   |-- resources
|   |   |   |       |-- bpmn
|   |   |   |       |-- dmn
|   |   |   |       |-- config
|   |   |   |         |-- document
|   |   |   |         |-- form
|   |   |   |         |-- form-flow
|   |   |   |         |-- form-link
|   |   |   |         |-- liquibase
|   |   |   |         |-- proces-document-link
|   |   |   |         |-- application.yml
|   |   |-- frontend
|   |   |   |-- app
|   |   |   |-- assets
|   |   |   |-- environments
|   |   |   |-- package.json
|   |   |-- README.md
|   |-- ...
|-- README.md
```

Almost all the files in `backend` can be copied into the back-end of an implementation project. The exceptions are:
* `application.yml`. This only includes the configurations required by the process blueprint. These should be merged
with the `application.yml` you already have.
* `build.gradle` or `pom.xml`. This only includes the dependencies required by the process blueprint. These should be
merged with the `build.gradle` or `pom.xml` you already have.

Almost all files in `frontend` can be copied into the front-end of an implementation project. The exceptions is:
*`package.json` . This only includes the dependencies required by the process blueprint. These shhould be merged with
the `package.json` you already have.

### Configuring and customizing the process blueprint

A process blueprint will not work out of the box. Plugins might need to be configured, and process links need to be set.
Each process blueprint comes with a README that explains the specifics that should be configured in order for the
process blueprint to be used. In addition to this, consider the following checklist:

* Check each task in the BPMN definition. Are all tasks defined correctly?
* If a task relies on a method for a specific spring bean, are both the bean and the method present?
* Does this process blueprint rely on plugins? If so, these will have to be configured, and process links will have to
be configured for the appropriate tasks as well.
* Does every user task have a form or form flow associated with it?
* If there are form flows, are all the forms it references present?

As always, be sure to follow the specific instructions that are included with the process blueprint.
