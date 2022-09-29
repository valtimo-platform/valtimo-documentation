# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Added extra parameter to KeycloakService**

  If your project has a custom implementation of the KeycloakService, your project might break due to a missing
  parameter in the constructor called `keycloakClientName`. The solution in simple: Just add an empty string for
  the `keycloakClientName` parameter. Or, a more elegant solution would look as follows:
  ```java
  public CustomKeycloakService(
      KeycloakSpringBootProperties properties,
      @Value("${valtimo.keycloak.client:}") String keycloakClientName
  ) {
      super(properties, keycloakClientName);
      this.properties = properties;
  }
  ```
