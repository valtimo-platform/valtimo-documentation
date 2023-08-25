# Objecten API Authentication

## Dependencies

In order to use the Objecten API Authentication plugin, the objecten-api-authentication module needs to 
be added as a dependency. The following can be added to your project, depending on whether Maven 
or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>objecten-api-authentication</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:objecten-api-authentication:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Objecten API Authentication plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
import { ObjectTokenAuthenticationPluginModule, objectTokenAuthenticationPluginSpecification } from '@valtimo/plugin';

@NgModule({
  imports: [
      ObjectTokenAuthenticationPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              objectTokenAuthenticationPluginSpecification,
          ]
      }
  ]
})
```
