# Architectural overview

## Tiers
Valtimo is a based on a three-tier architecture. 

-	The presentation tier is the user interface, based on Angular. It’s referred to as Frontend. 
-	The (business) logic tier is the heart of Valtimo, built in Kotlin/Java. It’s referred to as Backend.
-	For the data tier PostgreSQL (advised) and MySQL are supported.  

## Product v.s. implementation

An installation of the product is called an Implementation. In the backend an implementation is a Spring boot project. 
 
## Using a code repository & buildpipeline for building business processes

Developers can add models, configuration and code in the implementation. Models (DMN, BPMN in XML) and configuration (in JSON) are loaded in the database during startup. Working with a repository and CI/CD pipeline has the following advantages: 

-	Models and configuration are versioned in the repository. In this way, changes are tracked and quality can be improved by adding review processes. 
-	Developers have flexibility. The options for managing models and configuration files via the User Interfaces are limited. Using an integrated development environment (IDE) offers full flexibility. 
-	Tests can be executed at build time, adding an extra layer of quality insurance. 

Code always needs to be added in the implementation. For security reasons Valtimo does not offer hot deployment. 

## User Interface for business process modelling

The user interface offers the option to build and maintain models & configuration. Models and configuration are stored in the database. Working this way has the advantage of agility: models & configuration can be changed realtime, without the need for development experience. 

The functionality offered is limited. It is advised to use the UI for fast prototyping and in maintenance scenario’s. Typically, building business critical production processes is done via an IDE, repository and CI/CD pipeline.  

Note: when files exist in both the database and repository, the files in the repo will overwrite the files in the database at deployment. It is advised to define a strategy to have developers and system admins working together smoothly. 

## Plugin framework
The plugin framework is available. Is has advantages: 

-	 for integrating extra functionality into the product, offering ease in development and backwards compatibility. 
