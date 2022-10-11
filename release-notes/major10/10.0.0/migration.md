# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Java 17**
    
    Scope: Backend
    
    In order to run Valtimo a Java 17 environment must be used. The way to configure this is different per implementation.
    For example, the Java version used when gradle with gradle can be set like this:
    
    ```groovy
    sourceCompatibility = JavaVersion.VERSION_17
    targetCompatibility = JavaVersion.VERSION_17
    ```
    
    Also make sure that when building to a docker container a base image is used that supports Java 17.

* **Node.js and NPM version upgrade**
  
  Scope: Frontend

    1. **Configure NVM on your machine**

       In order to switch between the Node.js version your machine uses, it is recommended to use NVM. Please refer to
       [this page](https://github.com/nvm-sh/nvm) on how to configure NVM on macOS or Linux, and refer to [this page](https://github.com/coreybutler/nvm-windows#bulb-why-another-version-manager) on
       how to configure it on windows.
    2.  **Install Node.js version 18**
  
       Run `nvm install 18` inside a terminal to install the latest version of Node.js version 18. Afterwards, the
       terminal should print exactly which version has been installed:
       `Now using node v18.10.0 (npm v8.19.2)` (the version printed in your terminal might differ slightly).

    3. **Use Node.js version 18**

       After you installed the latest version 18, copy over the exact version number (in this example, it was 18.10.0)
       and run it in a `nvm use ...` command like so: `nvm use 18.10.0`. Your machine should now use Node.js version 18.


* **Angular upgrade**

  Scope: Frontend

    In order to use the new front-end libraries based on Angular version 14 in an implementation, run the following
    command in the root of the implementation project:
    `ng update @angular/core@14 @angular/cli@14 @angular-eslint/schematics`

       
