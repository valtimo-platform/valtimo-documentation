# Verzoek

This plugin makes it possible for Valtimo to create a Valtimo case with a GZAC zaak when a notification is received
from the Notificaties API.

## Dependencies

In order to use the Verzoek plugin, the Verzoek module needs to be added as a dependency. The following can be added to
your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:

```xml

<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>verzoek</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:

```groovy
dependencies {
    implementation "com.ritense.valtimo:verzoek:${valtimo_version}"
}
```


