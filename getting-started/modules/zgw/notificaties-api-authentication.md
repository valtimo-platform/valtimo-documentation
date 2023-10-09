# Notificaties API Authentication

## Dependencies

In order to use the Notificaties API Authentication plugin, the notificaties-api-authentication module needs to
be added as a dependency. The following can be added to your project, depending on whether Maven
or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>notificaties-api-authentication</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:notificaties-api-authentication:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the Notificaties API Authentication plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
import { OpenNotificatiesPluginModule, openNotificatiesPluginSpecification } from '@valtimo/plugin';

@NgModule({
    imports: [
        OpenNotificatiesPluginModule,
    ],
    providers: [
        {
            provide: PLUGIN_TOKEN,
            useValue: [
                openNotificatiesPluginSpecification,
            ]
        }
    ]
})
```
