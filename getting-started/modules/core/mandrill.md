# Mandrill

## Dependencies

In order to send emails with the Mandrill API, the Mandrill module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>mandrill</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:mandrill:${valtimo_version}"
}
```

## Configuration

In order to run the Haalcentraal BRP module, several properties can be configured. The bare minimum that has to be added to the
application properties is the following:

#### **`application.yml`**
```yaml
valtimo:
  mandrill:
    api-key:
    api-test-key:
    date-format:
    notification-template:
    completion-template:
    webhook-authentication-key:
    webhook-url:
```
