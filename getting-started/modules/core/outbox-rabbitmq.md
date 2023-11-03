# Outbox

## Dependencies

The `outbox-rabbitmq` module provides an outbox message publisher for RabbitMQ. 

### Backend

#### Maven dependency:

```xml

<dependencies>
  <dependency>
    <groupId>com.ritense.valtimo</groupId>
    <artifactId>outbox-rabbitmq</artifactId>
    <version>${valtimo_version}</version>
  </dependency>
</dependencies>
```

#### Gradle dependency:

```groovy
dependencies {
    implementation "com.ritense.valtimo:outbox-rabbitmq:${valtimo_version}"
}
```

## Configuration

In order to use this module, the following configuration properties need to be added to the application properties. Please adjust values to match the environment:

#### **`application.yml`**
```yaml
spring:
  rabbitmq:
    host: localhost
    port: 5672
    username: guest
    password: guest
    ssl.enabled: true # Optional. Defaults to false
    publisher-confirm-type: correlated # required value
    publisher-returns: true # required value

valtimo:
  outbox:
    publisher:
      rabbitmq:
        routingKey: valtimo-audit # change to queue name or routing key
        delivery-timeout: "PT0.5S"
```
