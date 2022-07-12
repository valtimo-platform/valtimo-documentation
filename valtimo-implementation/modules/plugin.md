# Plugins

## Dependencies

In order to use plugins or create custom plugin definitions, the plugin module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>plugin</artifactId>
        <version>9.14.0.RELEASE</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
    implementation "com.ritense.valtimo:plugin:9.14.0.RELEASE"
}
```


### Frontend

```json
{
  "dependencies": {
    "@valtimo/plugin-management": "5.2.0"
  }
}
```


