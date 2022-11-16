# Create your own Valtimo implementation

Last update: 16-11-2022
Reading time: 10 minutes
Setup time: 1 hour
Needed: Laptop (Mac/Windows) & A fast internet connection
 
## Intro
This guide provides information on how to setup a local Valtimo implementation. This quick guide will provide the essential information needed to setup your local development tools, how to get access to the code and shows how to run Valtimo locally. 
 
⚠️ This manual is meant for people that want to develop / contribute to the Valtimo platform. If you are looking how to run a Valtimo instance locally, please consult the [public guide](www.valtimo.nl) instead.
 
⚠️ There are two editions of Valtimo: ‘Valtimo-core’ and ‘GZAC’. The ‘GZAC’ edition is a special Valtimo implementation meant for government organizations. At the moment of publication, this guide only works for the ‘GZAC’ Valtimo development environment. This due to a problem with the docker containers for the ‘Valtimo’ edition. For this reason, this guide is ‘GZAC’ focused. 

## Table of content:
1. Install the needed tools
2. Setup Valtimo locally
•	Docker
•	Frontend
•	Backend
3. Common issues
 
## 1. Install the needed tools
 
There are several tools needed. See the list bellow which tools are needed and where do download them:
- [Git](https://git-scm.com/downloads)
- [Github desktop (optional)](https://desktop.github.com/)
- [IntelliJ](https://www.jetbrains.com/idea/download/)
- [Docker (Desktop)](https://www.docker.com/products/docker-desktop/)
- [NPM Package manager / NodeJS (version 16 or higher)](https://nodejs.org/en/download/)
- [Angular CLI](https://angular.io/cli)
 
## 2. Setup Valtimo locally
 
To develop and run Valtimo locally, you need three components: The backend, the frontend and the Docker containers. 
 
### Frontend
1. Clone the repository **Valtimo-frontend-libraries** from the public [Valtimo frontend github page](https://github.com/valtimo-platform/valtimo-frontend-libraries)
2. When the repository is cloned, open the cloned project in IntelliJ. It takes a some time to load the project and some scripts will run in the background when you open it. Please wait until the scripts are done before you continue.
3. Open the terminal and navigate to the 'Valtimo-frontend-libraries' folder. If you reached the folder, run the command (This can take a while):
```
npm install 
```
4. When the terminal is finished running this command, run the following command (This also will take a while):
```
npm run libs-build-all
``` 
5. If this command is finished, your frontend is ready to go. Start the frontend with 
```
npm start
``` 
By default, the application will be hosted on 'localhost:4200'. Valtimo does not work yet, only the frontend / ui will.
 
### Docker:
1. Make sure docker is running. If you use docker desktop, simply open the program.
2. Clone the repository **valtimo-docker-profiles** from the public [Valtimo docker github page](https://github.com/valtimo-platform/valtimo-docker-profiles)
3. When you cloned the repository, open this project in IntelliJ, just like the frontend libraries. 
4. Open your terminal and navigate to the `GZAC-Platform` folder 
5. The `docker-compose` file is located in this folder. This file tells docker what and how images should be installed. Run the command 
```
docker compose up
``` 
to let docker install the required images. This takes quite a while.
6. The first time, it takes a lot of time to pull all images. This will go faster all the other times. Some containers start up and end after a short while, this is on purpose.
 
### Backend
1. Clone the repository **valtimo-backend-libraries** from the public [Valtimo backend github page](https://github.com/valtimo-platform/valtimo-backend-libraries)
2. Open the repositoy with IntelliJ as a project. Serveral scripts will start running. Wait until these scripts are done before you continue.
3. Open the `Gradle` tab on the right side of the screen. Click the `Refresh` icon.
4. Build the project, using the `hammer` icon.
5. Make sure your frontend application is running, and that your docker contrainers are running. 
6. Open the Gradle tab again, open in this tab the folder:
```
'App' > gzac > 'Tasks' > 'Application'
``` 
A task called 'bootRun' is located in here. Click it twice to start the backend libraries. Note: use the same one as in the docker profiles repo. 
If you used valtimo-core start valtimo-core with bootrun
If you used gzac start gzac with bootrun 
 
The application runs locally on ‘localhost:4200’, the credentials (login/password) are **admin** for both fields.

## Possible complications
 
### Backend library issue: Run Gradle gives and error message:  'Invalid Gradle JDK configuration'
o	Problem: Invalid Gradle JDK configuration found. project-jdk-name is not defined.
o	Solution: change settings. Go to Settings > Preferences > Build, excecution & deployment > Build tools > Gradle > Change Gradle JVM to Azul 13
o	Context: For now, use JDK Azul 13. Later this will be changed to JDK 17 when Valtimo is upgraded to this verion. 