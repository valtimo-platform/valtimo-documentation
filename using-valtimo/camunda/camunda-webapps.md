# Configuring camunda webapps

By default Valtimo includes the camunda webapps, including the [cockpit](https://camunda.com/platform-7/cockpit/). 
This is accessible by using the path `/camunda/app` on the domain where valtimo is hosted. 
e.g. `http://example.valtimo.com/camunda/app`

## Configuring an admin user

The camunda webapps use the default camunda authentication mechanism. This means they cannot be accessed by keycloak
users. Credentials can be configured in the default way camunda provides when using spring. 

In order to create an admin user the follow application configuration should be set:
```yaml
camunda.bpm.admin-user:
    id: admin # or another username of choice 
    password: # enter a newly generated password here
```

See the
[camunda documentation](https://docs.camunda.org/manual/latest/user-guide/spring-boot-integration/configuration/#camunda-engine-properties)
for more configuration properties.

## Additional security

The camunda webapps are available in a separate path (`/camunda/*`) from the other valtimo apis (`/api/*`). Since the 
camunda webapps are a tool used to manage the internal it may be advisable to control access to this path on an 
infrastructure level.

To remove the camunda webapps from valtimo altogether the 
`org.camunda.bpm.springboot:camunda-bpm-spring-boot-starter-webapp:7.14.0` dependency can be excluded. This is a 
dependency in the valtimo `core` module.  
