# Valtimo dependencies

## Dependencies

In order to create an implementation, the Valtimo dependencies module can be added as a dependency. This includes the
most common modules that are used by Valtimo implementations. The following can be added to your project, depending on
whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.ritense.valtimo</groupId>
            <artifactId>valtimo-dependencies</artifactId>
            <version>${valtimo_version}</version>
        </dependency>
    </dependencies>
</dependencyManagement>

<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>valtimo-dependencies</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>

```

#### Gradle dependency:
```groovy
dependencies {
  implementation platform("com.ritense.valtimo:valtimo-dependencies:${valtimo_version}")
}

dependencyManagement {
  imports {
    mavenBom("com.ritense.valtimo:valtimo-dependencies:${valtimo_version}")
  }
}
```

### Dependencies

The following modules are added when a dependency on Valtimo dependencies is added:
* [Audit](audit.md)
* [Case](case.md)
* [Connector](connector.md)
* [Contract](contract.md)
* [Document](document.md)
* [Form](form.md)
* Form flow
* [Form flow Valtimo](form-flow.md)
* [Form links (deprecated)](form-link.md)
* Keycloak IAM
* Notes
* Plugin
* [Plugin Valtimo](plugin.md)
* [Process document](process-document.md)
* [Temporary resource storage](temporary-resource-storage.md)
* [Value resolver](value-resolver.md)
* [Web](web/web.md)
