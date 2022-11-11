# Start Valtimo as applications

## General instructions
The Valtimo platform consists of multiple services/containers. Depending on the edition (Valtimo or GZAC), a specific set of containers can be used for supporting a quick start-up.
For both editions, a Docker Compose repository is available. These repositories include a guide on which Compose file(s) to use and how to use them.

### Supporting services
Independent of the edition, Valtimo uses a Keycloak instance for Identity and Access Management. 
The Valtimo backend application requires a database container. Both PostgreSQL and MySQL are supported. 

### Application services
Valtimo consists of a frontend (Angular) and a backend (Java/Kotlin) application. Both services have their own Github repository with instructions on how the service can be started.

## Repositories

### Valtimo
For running Valtimo as applications, the following Github repositories can be used:
* valtimo-docker-compose (to be created)
* valtimo-backend-template (to be created)
* valtimo-frontend-template (to be created)

### GZAC
For running the Valtimo GZAC edition as applications, the following Github repositories can be used:
* [gzac-docker-compose](https://github.com/generiekzaakafhandelcomponent/gzac-docker-compose)
* [gzac-backend-template](https://github.com/generiekzaakafhandelcomponent/gzac-backend-template)
* [gzac-frontend-template](https://github.com/generiekzaakafhandelcomponent/gzac-frontend-template)
