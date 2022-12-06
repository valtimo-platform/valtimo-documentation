# Local mail

## Dependencies

In order to use the local mail implementation (e.g. for testing purposes), the local mail module needs to be
added as a dependency. The following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>local-mail</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:local-mail:${valtimo_version}"
}
```
