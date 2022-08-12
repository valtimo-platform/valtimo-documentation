# Plugins

## Dependencies

In order to use form links, the form link module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>form-link</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
    implementation "com.ritense.valtimo:form-link:${valtimo_version}"
}
```
