# Enabling the module

## Back end
Add the following dependency to your project's `build.gradle` file:

```gradle
dependencies {
    implementation 'com.valtimo:form-view-model:12.1.0'
}
```

## Front end

Add the following dependency to your project's `package.json` file:
```json
{
    "dependencies": {
        "@valtimo/form-view-model": "12.1.0"
    }
}
```
Enable the feature toggle in your project's environment.ts file and expose the token:
```typescript
featureToggles: {
    enableFormViewModel: true
}
```

```typescript
{
    provide: FORM_VIEW_MODEL_TOKEN,
    useValue: {component: FormViewModelComponent}
}
```

## UI

Enable the feature for a form via the process-link menu
![enable toggle](img/enable-toggle.png)
