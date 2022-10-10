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

* **Breaking change 2/Deprecation 2**

    1. **Step1**

       Description
    2. **Step2**

       Description
