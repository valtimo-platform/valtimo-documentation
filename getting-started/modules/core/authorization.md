# Authorization

## Dependencies

The authorization module is a transitive dependency of `core`, so no action should be necessary to enable the feature. 

However, if more control is needed the following can be added to your project:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>authorization</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:authorization:${valtimo_version}"
}
```


