# Script

## Dependencies

In order to use javascript, the plugin module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend
The samples below assume the [valtimo-dependency-versions](valtimo-dependency-versions.md) module is used.
If not, please specify the artifact version as well.

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>script</artifactId>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```kotlin
dependencies {
    implementation("com.ritense.valtimo:script")
}
```


### Frontend

#### Add dependency

Add the following dependency to the `package.json`:

```json
{
  "dependencies": {
    "@valtimo/script-management": "*.*.*"
  }
}
```

#### Add module

Add the `ScriptManagementModule` to the `app.module.ts`:

```typescript
...
import {ScriptManagementModule} from '@valtimo/script-management';
...

@NgModule({
    ...
    imports: [
        ...
        ScriptManagementModule,
        ...
    ],
    ...
})
export class AppModule {
...
```

#### Add menu item

Add 'Script' as a new admin menu item. This can be done in the environment.ts:

```typescript
...
export const environment: ValtimoConfig = {
  ...
  menu: {
    menuItems: [
      ...
      {
        roles: [ROLE_ADMIN], title: 'Admin', iconClass: 'icon mdi mdi-tune', sequence: 4, children: [
          ...
          {link: ['/script'], title: 'Scripts', sequence: 4},
          ...
        ]
      },
      ...
    ]
  }
};
...
```
