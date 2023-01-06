# Starting up Valtimo

## General information
The Valtimo platform consists of multiple services/containers. Depending on the edition (Valtimo or GZAC), a specific set of containers can be used for supporting a quick start-up.
For both editions, a Docker Compose repository is available. These repositories include a guide on which Compose file(s) to use and how to use them.

### Supporting services
Both editions of Valtimo require a Keycloak instance for Identity and Access Management.
The Valtimo backend application requires a database container. Both PostgreSQL and MySQL are supported.

### Application services
Valtimo consists of a frontend (Angular) and a backend (Java/Kotlin) application. Both services have their own Github repository with instructions on how the service can be started.

## Start up strategies
The Valtimo platform can be started in two ways:

### Start as Docker containers
When starting the Valtimo platform as Docker containers, all supporting services and the two Valtimo services are started up with a Docker Compose file. Instructions on how to start Valtimo as Docker containers can be found [here](start-as-docker-containers/start-as-docker-containers.md).

### Starting your own Valtimo implementation
When starting your own Valtimo implementation, the supporting services are started up with a Docker Compose file. The two Vatlimo services are started up from their respective Git repositories using a command line interface (CLI) or integrated development environment
(IDE). Instructions on how to start your own Valtimo implementation can be found [here](creating-your-own-valtimo-implementation/creating-your-own-valtimo-implementation.md).
