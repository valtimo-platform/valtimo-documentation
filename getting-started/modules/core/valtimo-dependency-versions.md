# Valtimo dependencies

## Dependencies

The `valtimo-dependency-versions` module specifies dependency versions for Valtimo.
When this module is used, please specify dependency versions only when needed. 

> NOTE: This dependency will not add any other dependencies to the classpath. It will only define the versions.
> 
> Please also take a look at [valtimo-dependencies](valtimo-dependencies.md) or [valtimo-gzac-dependencies](../zgw/valtimo-gzac-dependencies.md) when creating an implementation

This module specifies versions for:
- Valtimo 
  - GZAC
- Spring Boot
- Jackson
- Junit
- AWS SDK
- Liquibase
- Hibernate
- Shedlock
- Spring Boot Admin

For the full list, please take a look at the POM file of this module.

### Backend

#### Maven:
```xml
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.ritense.valtimo</groupId>
            <artifactId>valtimo-dependency-versions</artifactId>
            <version>${valtimo_version}</version>
        </dependency>
    </dependencies>
</dependencyManagement>
```

#### Gradle:
```groovy

dependencyManagement {
  imports {
    mavenBom("com.ritense.valtimo:valtimo-dependencies:${valtimo_version}")
  }
}
```
or
```groovy
dependencies {
    implementation(platform(project("com.ritense.valtimo:valtimo-dependencies:${valtimo_version}")))
}
```
