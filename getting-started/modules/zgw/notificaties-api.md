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

In order to use the Notificaties API plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
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


