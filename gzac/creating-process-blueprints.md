# Creating process blueprints for GZAC #
It is encouraged to share processes that can potentially be used by other municipalities. Another municipality can then implement the same process with minimal effort.

## Privacy and intellectual property
Sharing these processes is done through a public repository. This has some effects that a publisher should know before you continue.

Shared resources should not contain:
* any privacy- or security-sensitive information like:
  * Names, addresses or other data of real people.
  * Credentials of users or services
* the municipality name in code, labels, etc.
* licensed code that conflicts with the repository code

All submitted code will inherit the license of this repository. It is up to the publisher to include a copyright notice that is not in conflict with the license.

## Prerequisites
There are some things needed to be able to submit a blueprint:
* Access to all source files of a working process
* Git (https://git-scm.com/)
* An account on Github (https://github.com/signup)
* An IDE (optional), for instance:
  * Eclipse (https://www.eclipse.org/downloads/)
  * IntelliJ (https://www.jetbrains.com/idea/download/)

## Adding a blueprint to the repository
This is a step-by-step guide on how to submit a blueprint to the repository.

### Checkout the latest code
You can find the latest version of the blueprints repository [here](https://github.com/generiekzaakafhandelcomponent/Basisprocessen)

To check out the code using a terminal, use:
```
git clone https://github.com/generiekzaakafhandelcomponent/Basisprocessen
```

If you already have a copy, use `git pull` in the project directory to update it.

You can also check out the code using your IDE. Please check the vendors documentation on how to do that.

After checking out the code, the folder structure should look as follows:
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
|   |   |   |-- test
|   |   |       |-- java
|   |   |       |-- kotlin
|   |   |       |-- resources
|   |   |         |-- ...
|   |   |-- frontend
|   |   |   |-- app
|   |   |   |-- assets
|   |   |   |-- environments 
|   |   |   |-- ...
|   |   |-- README.md
|   |-- generiek-proces
|       |-- ...
|-- README.md
```

### Preparing your files ##
Before copying the files from the source project into the blueprints project, please make sure it complies with [Privacy and intellectual property](#privacy-and-intellectual-property) and the [coding guidelines](LINK NEEDED).
When changes have been made to native GZAC code or files, please only include the changes (snippets) and [write documentation](#write-documentation) on where to include them.

Be sure not to submit changes to your source project. Creating a separate branch would be one way to achieve that.

If some code cannot be shared, please provide an empty or simplified implementation in the code.

### Copy your files
1. create a new folder in `./blueprints` of the blueprints project with 
2. copy all files related to the new blueprint to the newly created folder. 
   * Please adhere to the given folder structure. 
   * only include files or folders that are specific for this blueprint. 

### Write documentation
Every blueprint should include a README.md covering the following topics:
* A summary of the process, including a visual representation of it.
* Prerequisites
  * Which version(s) of GZAC has this process been tested on
  * Which APIs, connectors, modules or plugins are needed.
* Instructions on (where applicable):
  * where to copy snippets of code to
  * how to configure the prerequisites
  * removed code that should be recreated

### Create a pull request
To finally share the code with other parties, a pull request (PR) should be created. Some of these can also be done using an IDE. These are the commands if you use a terminal:

Create a new branch:
```
git checkout -b feature/the-new-blueprint-name
```
Review the code to be comitted:
```
git status
```
Commit the changes to the local repository:
```
git add .
git commit . 'Added a blueprint: the-new-blueprint-name'
```
Push the code to the remote branch:
```
git push -u origin feature/the-new-blueprint-name
```
On [GitHub](https://github.com/generiekzaakafhandelcomponent/Basisprocessen), you should now be able to create a new pull request using your branch as a source. Make sure to set the destination to `main`.
