# Objecten API Authentication

## Dependencies

In order to use the OpenZaakPlugin for authentication, the `openzaak-plugin-authentication` module needs to 
be added as a dependency. The following can be added to your project, depending on whether Maven 
or Gradle is used:

### Backend
The samples below assume the [valtimo-dependency-versions](../core/valtimo-dependency-versions.md) module is used.
If not, please specify the artifact version as well.

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>openzaak-plugin-authentication</artifactId>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:openzaak-plugin-authentication"
}
```
