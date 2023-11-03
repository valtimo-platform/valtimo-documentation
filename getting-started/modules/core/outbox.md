# Outbox

## Dependencies

Valtimo contains an implementation of
the [transactional outbox pattern](https://microservices.io/patterns/data/transactional-outbox.html). To make use of
this pattern, the `outbox` module needs to be added as a dependency. The following can be added to your project,
depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:

```xml

<dependencies>
  <dependency>
    <groupId>com.ritense.valtimo</groupId>
    <artifactId>outbox</artifactId>
    <version>${valtimo_version}</version>
  </dependency>
</dependencies>
```

#### Gradle dependency:

```groovy
dependencies {
    implementation "com.ritense.valtimo:outbox:${valtimo_version}"
}
```

## Configuration

In order to use this module, the following configuration properties need to be added to the application properties. Please adjust values to match the environment:

#### **`application.yml`**
```yaml
valtimo:
  outbox:
    publisher:
      polling.rate: "PT1M" # ISO 8601 duration format
```
