# Custom form field data resolvers

Form field data resolvers allow for external fields to be referenced from inside a form. This can
be useful when retrieving document data, for example. A custom form field data resolver can be
created to support retrieving data from external sources.

## Implementing the FormFieldDataResolver 

Implementing the `FormFieldDataResolver` interface is required for custom form field data resolvers.
The `supports(String externalFormFieldType)` needs to be overridden, and corresponds to the prefix
that will be used in order to use this custom form field data resolver inside a form, e.g. `customPrefix.propertyName`.
Lastly, Spring bean needs to be declared for this class.

```java
public class CustomFormFieldDataResolver implements FormFieldDataResolver {

    // This method is deprecated, and does not have to be implemented more than this
    public boolean supports(ExternalFormFieldType externalFormFieldType) {
        return false;
    }

    @Override
    public boolean supports(String externalFormFieldType) {
        return "customPrefix".equals(externalFormFieldType);
    }

    public Map<String, Object> get(String documentDefinitionName, UUID documentId, String... varNames) {
        // Implementation of what this FormFieldDataResolver should do goes here
    }

}
```
