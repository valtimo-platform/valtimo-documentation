# Migrating to Spring Boot 3

The steps below will describe most relevant changes to Valtimo.
However, please also check the following guides when running into issues:
- [Spring Boot 3 Migration Guide](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Migration-Guide).
- [Preparing for Spring Security 6](https://docs.spring.io/spring-security/reference/5.8/migration/index.html).
- [Migrating to Spring Security 6](https://docs.spring.io/spring-security/reference/6.0/migration/index.html).

As a consequence of the Spring Boot 3 upgrade, some other frameworks / dependencies were also upgraded. 
Each chapter below describes the changes for the relevant framework or dependency.  

## Spring Boot 3 / Spring 6

- Java 8 is no longer supported. Please use Java 17.
- `spring.factories` have been [replaced](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Migration-Guide#auto-configuration-files) by `META-INF/spring/org.springframework.boot.autoconfigure.AutoConfiguration.imports`.
  - Listed configuration classes need to be annotated with `@AutoConfiguration`. More info can be found [here](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.7-Release-Notes#changes-to-auto-configuration)
- `@Controller` or `@RestController` annotations [are now mandatory](https://github.com/spring-projects/spring-framework/issues/22154).
  - When declaring the controller beans via autoconfiguration, please also annotate the controller with `com.ritense.valtimo.contract.annotation.@SkipComponentScan` to prevent duplicated beans.
- `javax` packages [changed](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Migration-Guide#jakarta-ee) to `jakarta`.
- `@ConstructingBinding` on  no longer supported/needed for `@ConfigurationProperties` classes.

## Spring Security 6

- `HttpSecurity.authorizeRequests` has been deprecated. 
  - When implementing the `HttpSecurityConfigurer`, this cannot be mixed with the replacement (`authorizeHttpRequests`).

Before:
```kotlin
http.authorizeRequests()
    .antMatchers(GET, "/api/v1/ping").permitAll()
```
New:
```kotlin
http.authorizeHttpRequests { requests ->
    requests.requestMatchers(antMatcher(GET, "/api/v1/ping")).permitAll()
}
```
- `WebSecurityConfigurerAdapter` has been removed.
  - Removed `CoreHttpSecurityConfigurerAdapter`. This has been replaced by `ValtimoCoreSecurityFactory`.
- `AuthorizedUrl.acccess(..)` no longer supports expressions as an argument.
  - `WhitelistIpRequest` has been replaced by `WhitelistIpRequestMatcher`. An example can be found in `CamundaCockpitHttpSecurityConfigurer`.
      
- Cockpit is now whitelist-secured again. Support for CIDRs added to support a range of addresses.
  - A list of hosts can be set at `valtimo.security.whitelist.hosts`.
- Removed `AuthenticationSecurityConfigurer`. No replacement other than implementing a `SecurityFilterChain` directly.
- OpenAPI endpoint `/v3/api-docs` is now only available to `ROLE_DEVELOPER`.

## Hibernate 6

- Overriding entity properties is no longer supported. 

  As a result, `ProcessLink` implementations can no longer be a `data` class and cannot override the base properties of `ProcessLink`. 
  
  Methods previously generated by the `data` type like `equals(other: Any?)`, `hashCode()` and `copy(...)` should be migrated accordingly.
- `SimpleJpaRepository.deleteById` never followed spec to ignore not-found entities. This has been fixed in Hibernate 6.  
  The existing endpoints will follow the new JPA behaviour to make the action idempotent:
  - DELETE /api/v1/choice-fields/{non-existent-id} -> 200
  - DELETE /api/v1/choice-field-values/{non-existent-id} -> 200
  - DELETE /api/management/v1/dashboard/{non-existent-id} -> 204
  - DELETE /api/v1/form-management/{non-existent-id} -> 204
- Changes to `application.yaml`:
  - Removal of `spring.jpa.hibernate.naming.physical-strategy`. No replacement needed.
  - Removal of `spring.jpa.hibernate.naming.implicit-strategy`. No replacement needed.
  - Removal of `spring.jpa.hibernate.use-new-id-generator-mappings`. No replacement needed.
- `AuditRecordRepository.findByEventAndDocumentId(List<Class<? extends AuditEvent>> eventTypes, UUID documentId, Pageable pageable);` changed to `AuditRecordRepository.findByEventAndDocumentId(List<String> eventTypes, UUID documentId, Pageable pageable);`

## Other   

- Camunda History TTL is now required by default. Either:
  - Set the [camunda:historyTimeToLive](https://docs.camunda.org/manual/7.20/reference/bpmn20/custom-extensions/extension-attributes/#historytimetolive) via the modeler or XML.
  - Set the application property `camunda.bpm.generic-properties.properties.enforceHistoryTimeToLive` to `false` if you don't want to enforce a TTL.
- Mockito 5 vararg matching [has changed](https://github.com/mockito/mockito/releases/tag/v5.0.0).