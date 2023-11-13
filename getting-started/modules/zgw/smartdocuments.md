# SmartDocuments

## Dependencies

In order to use SmartDocuments, the SmartDocuments module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>smartdocuments</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```groovy
dependencies {
  implementation "com.ritense.valtimo:smartdocuments:${valtimo_version}"
}
```

### Frontend

A general instruction to add a front-end plugin to the implementation can be
found [here](../core/plugin.md#adding-a-front-end-plugin-to-the-implementation).

In order to use the SmartDocuments plugin in the frontend, the following can be added to your `app.module.ts`:

```typescript
import { SmartDocumentsPluginModule, smartDocumentsPluginSpecification } from '@valtimo/plugin';

@NgModule({
  imports: [
      SmartDocumentsPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              smartDocumentsPluginSpecification,
          ]
      }
  ]
})
```
