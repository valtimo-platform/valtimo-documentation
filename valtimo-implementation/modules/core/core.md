# Core

## Dependencies

In order to use Valtimo, the core module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>core</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:core:${valtimo_version}"
}
```

## Configuration

In order to run the web module, several properties need to be configured. The bare minimum that has to be added to the
application properties are the following:

#### **`application.yml`**
```yaml
valtimo:
  jwt:
    base64encoding: false 
    tokenValidityInSeconds: 3600
    tokenValidityInSecondsForRememberMe: 2592000
    secret: "secret-goes-here"
```
 