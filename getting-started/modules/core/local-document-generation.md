# Local document generation

## Dependencies

In order to use local document generation (e.g. for testing purposes), the local document generation module needs to be
added as a dependency. The following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>local-document-generation</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:local-document-generation:${valtimo_version}"
}
```
