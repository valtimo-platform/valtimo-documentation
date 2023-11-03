# Besluiten API

## Dependencies

In order to use the Besluiten API, the Besluiten API module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>besluiten-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:besluiten-api:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Besluiten API plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
import { BesluitenApiPluginModule, besluitenApiPluginSpecification } from '@valtimo/plugin';

@NgModule({
  imports: [
      BesluitenApiPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              besluitenApiPluginSpecification,
          ]
      }
  ]
})
```

Before the Besluiten API plugin can be used, an authentication plugin is needed. One such authentication plugin is the
OpenZaak plugin. Instructions on how to add the OpenZaak plugin can be
found [here](openzaak.md).

