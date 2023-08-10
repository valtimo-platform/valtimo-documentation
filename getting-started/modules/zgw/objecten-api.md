# Objecten API

## Dependencies

In order to use the Objecten API, the Objecten API module needs to be added as a dependency. The
following can be added to your project, depending on whether Maven or Gradle is used:

### Backend

#### Maven dependency:
```xml
<dependencies>
    <dependency>
        <groupId>com.ritense.valtimo</groupId>
        <artifactId>objecten-api</artifactId>
        <version>${valtimo_version}</version>
    </dependency>
</dependencies>
```

#### Gradle dependency:
```json
dependencies {
  implementation "com.ritense.valtimo:objecten-api:${valtimo_version}"
}
```

### Frontend

In order to use the Objecten API plugin in the frontend the following can be added to your `app.module.ts`:

```typescript
@NgModule({
  imports: [
      ObjectenApiPluginModule,
  ],
  providers: [
      {
          provide: PLUGIN_TOKEN,
          useValue: [
              objectenApiPluginSpecification,
          ]
      }
  ]
})
```

