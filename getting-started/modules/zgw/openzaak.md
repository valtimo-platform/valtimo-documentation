# OpenZaak

## Dependencies

In order to use OpenZaak, the OpenZaak module needs to be added as a dependency.
The following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>openzaak</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:openzaak:${valtimo_version}"
}
```

### Using plugins

When a plugin is implemented in your project, the Openzaak module needs three additional dependencies:
- DocumentenApiAuthentication 
- ZakenApiAuthentication 
- CatalogiApiAuthentication

For this, the following needs to be added to your project:

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>documenten-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>zaken-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>catalogi-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:documenten-api:$valtimoVersion"
  implementation "com.ritense.valtimo:zaken-api:$valtimoVersion"
  implementation "com.ritense.valtimo:catalogi-api:$valtimoVersion"
}
```


