# Data provider

The data provider module exposes any kind of data through an API. An engineer can expose data by writing a data
provider. 

This module was created for a specific use-case: the admin of the application should be able to configure a
data source that should populate a dropdown list. The admin can pick any data provider from the ui, without any code
changes.

## Dependencies

In order to use data providers, the data provider module needs be added as a dependency. The following can be added to
your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:

```xml

<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>data-provider</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:

```json
dependencies {
  implementation
  "com.ritense.valtimo:data-provider:${valtimo_version}"
}
```
