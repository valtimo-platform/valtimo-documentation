# Plugins

## Dependencies

In order to use plugins or create custom plugin definitions, the plugin module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>plugin</artifactId>
        <version>9.14.0.RELEASE</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
    implementation "com.ritense.valtimo:plugin:9.14.0.RELEASE"
}
```


### Frontend

```json
{
  "dependencies": {
    "@valtimo/plugin-management": "*.*.*",
    "@valtimo/plugin": "*.*.*"
  }
}
```

####  Adding a front-end plugin to your implementation

For each plugin you configure in the back-end, your front-end implementation needs to know what components to use in
order to configure your plugin, and to configure your plugin's actions.

The library `@valtimo/plugin` exports several pre-made plugins. In order to use these in your implementation, you need
to import the plugin's module and the plugin's specification into your app module like so. Also, you need to import
`PLUGINS_TOKEN` to inject the specification.

For example:

#### **`app.module.ts`**
```typescript
...

import {
    PLUGINS_TOKEN,
    SmartDocumentsPluginModule,
    smartDocumentsPluginSpecification
} from '@valtimo/plugin';

...
```

Next, add the plugin module to the `imports` array of your app module, and add the specification to the array provided
by `PLUGINS_TOKEN` under the `providers` array in your app module.

For example:

#### **`app.module.ts`**
```typescript
...

@NgModule({
    ...
    imports: [
        ...
        SmartDocumentsPluginModule
    ],
    providers: [
        ...
        {
            provide: PLUGINS_TOKEN,
            useValue: [
                ...
                smartDocumentsPluginSpecification
            ],
        },
    ],
    ...
})
export class AppModule {
}
```
Your implementation should now be able to display the plugin, configure it, configure its actions, and be able to link
its actions to process activities.


