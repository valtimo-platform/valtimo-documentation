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
```json
dependencies {
  implementation "com.ritense.valtimo:zaken-api:${valtimo_version}"
}
```

### Frontend

In order to use the Zaken API plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
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


