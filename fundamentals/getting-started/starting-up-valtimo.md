# Starting up Valtimo

The Valtimo platform consists of multiple services/containers. Depending on the edition (Valtimo or GZAC), a specific set of containers can be used for supporting a quick start-up. For both editions, a Docker Compose repository is available. These repositories include a guide on which Compose file(s) to use and how to use them.

### Supporting services <a href="#supporting-services" id="supporting-services"></a>

Both editions of Valtimo require a Keycloak instance for Identity and Access Management. The Valtimo backend application requires a database container. Both PostgreSQL and MySQL are supported.

### Application services <a href="#application-services" id="application-services"></a>

Valtimo consists of a frontend (Angular) and a backend (Java/Kotlin) application. Both services have their own Github repository with instructions on how the service can be started.

## Start up strategies <a href="#start-up-strategies" id="start-up-strategies"></a>

The Valtimo platform can be started in two ways:

### Start as Docker containers <a href="#start-as-docker-containers" id="start-as-docker-containers"></a>

When starting the Valtimo platform as Docker containers, all supporting services and the two Valtimo services are started up with a Docker Compose file. The containers are designed for evaluation purposes only. Best results are made using an IDE. For creating production processes in Valtimo a CI/CD pipeline is required. See [Starting your own Valtimo implementation](starting-up-valtimo.md#starting-your-own-valtimo-implementation).

#### Repositories <a href="#repositories" id="repositories"></a>

Depending on the Valtimo edition, a Github repository should be checked out that contains the Docker Compose file. Instructions on how to start the Docker containers can be found in the README of the mentioned repositories.

{% tabs %}
{% tab title="Valtimo" %}
For starting the Valtimo platform, the following repository should be checked out:

* &#x20;[valtimo-docker-compose](https://github.com/valtimo-platform/valtimo-docker-compose)
{% endtab %}

{% tab title="Valtimo GZAC" %}
For starting the GZAC platform, the following repository should be checked out:

* [gzac-docker-compose](https://github.com/generiekzaakafhandelcomponent/gzac-docker-compose)
{% endtab %}
{% endtabs %}

### Starting your own Valtimo implementation <a href="#starting-your-own-valtimo-implementation" id="starting-your-own-valtimo-implementation"></a>

When starting your own Valtimo implementation, the supporting services are started up with a Docker Compose file. The two Valtimo services are started up from their respective Git repositories using a command line interface (CLI) or integrated development environment (IDE).&#x20;

#### Repositories <a href="#repositories" id="repositories"></a>

Depending on the Valtimo edition, three Github repositories should be checked out:

* Supporting Services
* Backend application
* Frontend application

{% tabs %}
{% tab title="Valtimo" %}
For starting a Valtimo implementation, the following Github repositories should be checked out:

* [valtimo-docker-compose](https://github.com/valtimo-platform/valtimo-docker-compose)
* [valtimo-backend-template](https://github.com/valtimo-platform/valtimo-backend-template)
* [valtimo-frontend-template](https://github.com/valtimo-platform/valtimo-frontend-template)
{% endtab %}

{% tab title="Valtimo GZAC" %}
For starting a GZAC implementation, the following Github repositories should be checked out:

* [gzac-docker-compose](https://github.com/generiekzaakafhandelcomponent/gzac-docker-compose)
* [gzac-backend-template](https://github.com/generiekzaakafhandelcomponent/gzac-backend-template)
* [gzac-frontend-template](https://github.com/generiekzaakafhandelcomponent/gzac-frontend-template)
{% endtab %}
{% endtabs %}
