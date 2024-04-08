# OpenZaak Resource
> **_NOTE:_** This module has been deprecated. Please use the [Documenten API module](documenten-api.md) instead.

## Dependencies

In order to upload documents, the OpenZaak resource module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend
The samples below assume the [valtimo-dependency-versions](../core/valtimo-dependency-versions.md) module is used.
If not, please specify the artifact version as well.

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>openzaak-resource</artifactId>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```kotlin
dependencies {
  implementation("com.ritense.valtimo:openzaak-resource")
}
```
