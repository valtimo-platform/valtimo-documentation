# Whitelisting Spring beans

Form flows can contain SpEL expressions. These expressions can make use of Spring beans. This page shows how Spring
beans can be used by Form flow expressions.

## FormFlowBean annotation

Spring Expression Language (SpEL) by default allows access to Spring beans, e.g. to retrieve data from
an external source. Valtimo uses a whitelist for this instead, as exposing every bean is a security concern.
In order to add a Spring bean to this whitelist, the class itself has to be whitelisted. This is done with
the `@FormFlowBean` annotation.

1. Ensure a bean for the class that should be whitelisted is provided.

   ```java
   @Bean
   public SomethingService somethingService() {
      return new somethingService();
   }
   ```

2. At the top of the class, add the `@FormFlowBean` annotation.

   ```java
   @FormFlowBean
   public class SomethingService {
      ...
   }
   ```

The bean can now be used. For information on how to use these beans inside of a form flow definition,
see [here](/using-valtimo/form-flow/create-form-flow-definition.md).
