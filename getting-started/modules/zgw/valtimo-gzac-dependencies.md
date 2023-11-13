# Valtimo GZAC dependencies

## Dependencies

In order to create an implementation using the GZAC edition, the Valtimo GZAC dependencies module can be added as a
dependency. This includes the most common modules that are used by Valtimo GZAC implementations, including the [Valtimo
dependencies](../core/valtimo-dependencies.md). The following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.ritense.valtimo</groupId>
            <artifactId>valtimo-gzac-dependencies</artifactId>
            <version>${valtimo_version}</version>
        </dependency>
    </dependencies>
</dependencyManagement>

<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>valtimo-gzac-dependencies</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>

```

#### Gradle dependency:
```groovy
dependencies {
  implementation platform("com.ritense.valtimo:valtimo-gzac-dependencies:$valtimo_version")
}

dependencyManagement {
  imports {
    mavenBom("com.ritense.valtimo:valtimo-gzac-dependencies:${valtimo_version}")
  }
}
```

### Dependencies

The following modules are added when a dependency on Valtimo GZAC dependencies is added:
* [Valtimo dependencies](../core/valtimo-dependencies.md)
* [Besluit](besluit.md)
* [Catalogi API](catalogi-api.md)
* [Contactmoment](contactmoment.md)
* [Documenten API](documenten-api.md)
* [Haalcentraal BRP](haalcentraal-brp.md)
* [Klant](klant.md)
* Notificaties API
* Notificaties API authentication
* Object management
* [Objecten API](objecten-api.md)
* [Objecten API authentication](objecten-api-authentication.md)
* [Objects API](objects-api.md)
* [Objecttypen API](objecttypen-api.md)
* [Openzaak](openzaak.md)
* [Openzaak](openzaak-resource.md)
* Verzoek
* [Zaken API](zaken-api.md)
