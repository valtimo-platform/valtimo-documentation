# Zaken API

## Dependencies

In order to use the Zaken API, the Zaken API module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>zaken-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:zaken-api:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be 
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Zaken API plugin in the frontend, the following can be added to your `app.module.ts`:

```typescript
import {ZakenApiPluginModule, zakenApiPluginSpecification} from '@valtimo/plugin';

@NgModule({
  imports: [
      ZakenApiPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              zakenApiPluginSpecification,
          ]
      }
  ]
})
```

Before the Zaken API plugin can be used, an authentication plugin is needed. One such authentication plugin is the
OpenZaak plugin. Instructions on how to add this plugin can be
found [here](openzaak.md).
