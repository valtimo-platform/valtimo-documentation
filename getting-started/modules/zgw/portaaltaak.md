# Portaaltaak
This plugin makes it possible for Valtimo to communicate and interact with a Portaaltaak specification compliant ZGW component.

## Dependencies

In order to use the Portaaltaak, the Portaaltaak module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>portaaltaak</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:portaaltaak:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Portaaltaak plugin in the frontend, the following can be added to your `app.module.ts`:

```typescript
import { PortaaltaakPluginModule, portaaltaakPluginSpecification } from '@valtimo/plugin';

@NgModule({
  imports: [
      PortaaltaakPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              portaaltaakPluginSpecification,
          ]
      }
  ]
})
```
