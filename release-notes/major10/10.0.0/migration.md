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

* **View configurator**

  Scope: Backend

  The view configurator module has been removed. This module has not been supported by the front-end since Valtimo 5
  and any implementation that has this on the classpath can remove this module. Any implementation that has had this 
  module on the classpath can run this database script for 
  [MySQL](https://github.com/valtimo-platform/valtimo-migration/blob/main/10.0.0/mysql/valtimo-migration-view-configurator-10.0.0-mysql.sql) 
  or 
  [PostgreSQL](https://github.com/valtimo-platform/valtimo-migration/blob/main/10.0.0/postgresql/valtimo-migration-view-configurator-10.0.0-postgres.sql) 
  to clean up the database.

* **Process data object relation**

  Scope: Backend

  Process data object relations have been removed. Any implementation that has entities that extend the
  `IProcessDataObject` class are to remove this interface and store the data in their document definition instead. This
  data can be the entity or a reference to the entity, and has to be migrated before upgrading to this version of 
  Valtimo.

  Additionally, the following database script should be used for [MySQL](https://github.com/valtimo-platform/valtimo-migration/blob/main/10.0.0/mysql/valtimo-migration-process-data-object-10.0.0-mysql.sql) 
  or [PostgreSQL](https://github.com/valtimo-platform/valtimo-migration/blob/main/10.0.0/mysql/valtimo-migration-process-data-object-10.0.0-postgres.sql)
  to clean up the database.

* **Angular upgrade**

  Scope: Frontend

    In order to use the new front-end libraries based on Angular version 14 in an implementation, run the following
    command in the root of the implementation project:
    `ng update @angular/core@14 @angular/cli@14`

* **REST API versioning**

  Scope: Front-end and back-end

  Versioning has been introduced for every REST endpoint exposed by Valtimo. If your implementation manually makes calls
  to currently existing Valtimo endpoints, these will have to be changed, e.g. `/api/document` becomes 
  `/api/v1/document`.
