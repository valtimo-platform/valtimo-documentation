# Notificaties API

## Dependencies

In order to use the Notificaties API, the Notificaties API module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>notificaties-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:notificaties-api:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Notificaties API plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
import { NotificatiesApiPluginModule, notificatiesApiPluginSpecification } from '@valtimo/plugin';

@NgModule({
  imports: [
      NotificatiesApiPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              notificatiesApiPluginSpecification,
          ]
      }
  ]
})
```

Before the Notificaties API plugin can be used, an authentication plugin is needed. One such authentication plugin
is the Notificaties API authentication plugin. Instructions on how to add this plugin can be
found [here](notificaties-api-authentication.md).
