# Contract

## Dependencies

In order to create and use custom Valtimo components, the contract module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend
The samples below assume the [valtimo-dependency-versions](valtimo-dependency-versions.md) module is used.
If not, please specify the artifact version as well.

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>contract</artifactId>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```kotlin
dependencies {
  implementation("com.ritense.valtimo:contract")
}
```

## Configuration

Contract can be configured to better match the environment. The identifier field used when assigning cases and tasks to
users can be configured with the property as defined below:

#### **`application.yml`**
```yaml
valtimo:
  oauth:
    identifier-field: username
```

There are two possible values here, `username` and `userid`. These settings should only be configured once, when setting
up Valtimo. Changing this property to something else will also require database changes.
