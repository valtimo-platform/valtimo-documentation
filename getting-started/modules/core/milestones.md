# Milestones

## Dependencies

In order to use milestones, the milestones module needs to
be added as a dependency. The following can be added to your project, depending on whether Maven
or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>milestones</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:milestones:${valtimo_version}"
}
```
