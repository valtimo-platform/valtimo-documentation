# Whitelisting Spring beans for Camunda

It is possible to use custom code in your BPMN processes by referencing a [Spring bean](https://docs.spring.io/spring-framework/docs/current/reference/html/core.html)
that contains the code you want to run. Any spring bean can be used in expressions by using the bean name.

## ProcessBean annotation

Camunda by default allows access to Spring beans, e.g. to send an email. Valtimo provides a whitelist for this instead,
as exposing every bean is a security concern. In order to add a Spring bean to this whitelist, the bean definittion
itself has to be whitelisted. This is done with the `@ProcessBean` annotation.

1. Set the whitelist configuration property to `true`.

   #### **`application.yml`**
   ```yaml
   valtimo:
     camunda:
       bean-whitelisting: true
   ```

2. Ensure a bean for the class that should be whitelisted is provided.

   ```java
   @Bean
   public SomethingService somethingService() {
      return new somethingService();
   }
   ```

3. Add the `@ProcessBean` annotation.

   ```java
   @Bean
   @ProcessBean
   public SomethingService somethingService() {
      return new somethingService();
   }
   ```

The bean can now be used. For information on how to use these beans inside a BPMN,
see [here](/extending-valtimo/integrate-spring-bean-in-process.md).
