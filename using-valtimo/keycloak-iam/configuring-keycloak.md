# Configuring Keycloak

Keycloak is the default authentication provider for Valtimo. It is used to authenticate users, and Valtimo can 
retrieve information about users and roles from Keycloak.

## Properties for connecting to Keycloak

In order for Valtimo to connect to Keycloak, certain properties are necessary. There are two different location in
which these properties can be placed.

The properties can be placed in the `application.yml`:

```yaml
keycloak:
  realm: valtimo
  auth-server-url: https://keycloak.example.com/auth
  resource: valtimo-user-m2m-client
  credentials:
    secret: # It's recommended to store this property in an environment variable
```

Or as an environment variable:

```properties
KEYCLOAK_REALM=valtimo
KEYCLOAK_AUTH-SERVER-URL=https://keycloak.example.com/auth
KEYCLOAK_RESOURCE=valtimo-user-m2m-client
KEYCLOAK_CREDENTIALS_SECRET=0000000-1111-2222-3333-444444444444
```

More information about these properties and other optional properties can be
found [here](https://www.keycloak.org/docs/latest/securing_apps/#_java_adapter_config).

## Client roles

By default, Valtimo uses Keycloak _realm_ roles. But Valtimo can be configured to also use the Keycloak _client_ roles.
To make use of Keycloak client roles together with the realm roles, the following property is needed:

```yaml
valtimo:
  keycloak:
    client: valtimo-console
```

or

```properties
VALTIMO_KEYCLOAK_CLIENT=valtimo-console
```

## Keycloak token authentication

When keycloak is used as authentication provider for Valtimo, the public key from Keycloak needs to be configured 
in order to validate the JWT tokens. The public key can be provided by configuring the following environment 
variable:

```properties
VALTIMO_OAUTH_PUBLIC_KEY=MIIBI/EXAMPLE//PUBLIC+KEY
```
