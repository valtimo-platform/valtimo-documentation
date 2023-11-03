# Klant

## Dependencies

In order to connect to the Klanten API, the klant module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>klant</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:klant:${valtimo_version}"
}
```

## Configuration

In order to run the klant module, several properties can be configured. The bare minimum that has to be added to the
application properties is the following:

#### **`application.yml`**
```yaml
valtimo:
  openklant:
    url:
    client-id:
    secret: 
    rsin: 
```
