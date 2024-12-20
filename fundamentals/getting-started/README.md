# 🖱️ Getting started

This section contains information on how to create a new Valtimo implementation. Instructions are available for two types of user groups that want to get started with Valtimo:

* Business Process Engineers
* Software Developers

The Valtimo platform consists of multiple services/containers. Depending on the edition (Valtimo or GZAC), a specific set of containers can be used for supporting a quick start-up. For both editions, a Docker Compose repository is available. These repositories include a guide on which Compose file(s) to use and how to use them.

### **Business Process Engineers**

Available documentation for users that want to use Valtimo as an "Off the Shelf" application and do not want to be bothered with technical documentation on the setup and configuration of the environment.

In order to enable these users, instruction video's are recorded and made available in the online [Valtimo Academy](https://academy.valtimo.nl) on how to make use of GIT and Docker Desktop to start up Valtimo on your own device (laptop or PC). The UI versions of the training material both have a first chapter that explains how to setup Valtimo on your own device in about 15 minutes.

* [Introduction training for Business Process Engineers](https://academy.valtimo.nl/courses/introductietraining-voor-business-process-engineers-ui-versie-v12)\*
* [Create a Case definition](https://academy.valtimo.nl/courses/maken-van-dossier-definitie-ui)\*

_\* This training material is recorded in Dutch._

#### For experienced users

For users that are already familiar with GIT and Docker Desktop, instructions are available in the README files of below mentioned repositories. Depending on the Valtimo edition, a Github repository should be checked out that contains the Docker Compose file.

{% tabs %}
{% tab title="Valtimo" %}
For starting the Valtimo platform, the following repository should be checked out:

* &#x20;[valtimo-docker-compose](https://github.com/valtimo-platform/valtimo-docker-compose)
{% endtab %}

{% tab title="GZAC" %}
For starting the GZAC platform, the following repository should be checked out:

* [gzac-docker-compose](https://github.com/generiekzaakafhandelcomponent/gzac-docker-compose)
{% endtab %}
{% endtabs %}

When starting the Valtimo platform as Docker containers, all supporting services and the two Valtimo services are started up with above Docker Compose files. The containers are designed for evaluation purposes only.\


### **Software developers**

Documentation for tech-savvy engineers and developers on which modules are available and what settings at minimum are required to use them. Some knowledge on java build tools such as [Maven](https://maven.apache.org/) or [Gradle](https://gradle.org/) is assumed for these users.

#### Starting your own Valtimo implementation

When starting your own Valtimo implementation, the supporting services are started up with a Docker Compose file. The two Valtimo services are started up from their respective Git repositories using a command line interface (CLI) or integrated development environment (IDE).&#x20;

#### Supporting services

Both editions of Valtimo require a Keycloak instance for Identity and Access Management. The Valtimo backend application requires a database container. Both PostgreSQL and MySQL are supported.

#### Application services <a href="#application-services" id="application-services"></a>

Valtimo consists of a frontend (Angular) and a backend (Java/Kotlin) application. Both services have their own Github repository with instructions on how the service can be started.

#### **Repositories** <a href="#repositories" id="repositories"></a>

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

Instructions are available in the README files of above mentioned repositories.
{% endtab %}

{% tab title="GZAC" %}
For starting a GZAC implementation, the following Github repositories should be checked out:

* [gzac-docker-compose](https://github.com/generiekzaakafhandelcomponent/gzac-docker-compose)
* [gzac-backend-template](https://github.com/generiekzaakafhandelcomponent/gzac-backend-template)
* [gzac-frontend-template](https://github.com/generiekzaakafhandelcomponent/gzac-frontend-template)

Instructions are available in the README files of above mentioned repositories.&#x20;
{% endtab %}
{% endtabs %}

\
Below pages contain additional information for engineers and developers for making choices in database type, available modules and an overview of tested versions in a compatibility matrix.

* [Configuring the database](configure-database.md)
* [Modules](modules/)
* [Compatibility matrix](compatibility-matrix.md)
