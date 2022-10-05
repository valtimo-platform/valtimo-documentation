# Haalcentraal BRP

## Dependencies

In order to connect to the Haalcentraal BRP, the Haalcentraal BRP module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>haalcentraal-brp</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:haalcentraal-brp:${valtimo_version}"
}
```
