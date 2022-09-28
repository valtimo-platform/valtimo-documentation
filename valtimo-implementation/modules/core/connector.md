# Connector

## Dependencies

In order to create and use connectors, the connector module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>connector</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:connector:${valtimo_version}"
}
```

## Configuration

In order to run the connector module, the `valtimo.connector-encryption.secret` property needs to be configured. The bare
minimum that has to be added to the application properties are the following:

#### **`application.yml`**
```yaml
valtimo:
  connector-encryption:
    secret: "<your-value-goes-here>"
```
 