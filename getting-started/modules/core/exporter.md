# Exporter

## Dependencies

In order to do custom exports, the exporter module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>exporter</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
    implementation "com.ritense.valtimo:exporter:${valtimo_version}"
}
```
