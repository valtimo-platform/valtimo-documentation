# Creating a form field data resolver

A `FormFieldDataResolver` is a spring bean that is used by Valtimo to get data to be preloaded in a form.
By adding a new implementation of the `FormFieldDataResolver` interface and registering this as bean a new prefix can 
be supported. 

There are two methods that need to be implemented:
- The `supports(String externalFormFieldType)` method determines whether if the current resolver is applicable for a 
certain prefix. When `true` is returned it means the current resolver supports the prefix that Valtimo has found and 
the get method will be called.
- The `get(String documentDefinitionName, UUID documentId, String... varNames)` method is used by Valtimo get retrieve
the actual data. `documentDefinitionName` and `documentId` are passed in as context that can be used to find the data
for the current form. Any fields in the form that use the same prefix will be bundled and the will be passed in this
method as the varargs parameter `varNames`. The intention is to be able to bundle calls to other systems and resources
in order to reduce load and load times (e.g., retrieve a database record once, and get multiple properties from the
  result). The result of this method is a `Map<String, Object>` where the key is the name of the field (one entry from 
the `varNames`) and the value is the value that needs to be loaded in the form.

Below is an example of what a `FormFieldDataResolver` could look like. This example would be called for each formfield
where the `example` prefix is used (e.g., `example:some-field`). 

```java
public class ExampleDataResolver implements FormFieldDataResolver {
    private static final String PREFIX = "example";

    @Override
    public boolean supports(String externalFormFieldType) {
        return externalFormFieldType.equals(PREFIX);
    }

    @Override
    public Map<String, Object> get(String documentDefinitionName, UUID documentId, String... varNames) {
        // get values for all requested variables
    }
}
```