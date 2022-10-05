# Process document

## Dependencies

In order to link a document to a process or reference document fields from inside a process , 
the process document module needs to be added as a dependency. The following can be added to your
project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>process-document</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
    implementation "com.ritense.valtimo:process-document:${valtimo_version}"
}
```
