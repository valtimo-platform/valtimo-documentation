# Troubleshoot

## Documents

### "Invalid JSON path expression" when searching for a document

MySQL documentation states "Names of keys must be double-quoted strings or valid ECMAScript identifiers". As a rule of
thumb, if the property contains a hyphen, then the property should have quotes surrounding it.

Searching for `"$.order.order-id"` becomes `"$.order.\"order-id\""`.

## Form.IO

### Front-end

#### Custom Form.IO components are not loading

In implementations, custom Form.IO components can be registered in the `AppModule` like so:

#### **`app.module.ts`**

```typescript
...
export class AppModule {
    constructor(injector: Injector) {
        // function to register custom component
        registerFormioUploadComponent(injector);
    }
}
```

The use of these custom components is only possible if Form.IO is imported through `FormIoModule` from 
`@valtimo/components`. Additional imports of Form.IO - for example through `FormioModule` from `@formio/angular` -
breaks the use of these custom components.

## Dependencies

### Front-end

#### @types/node

Version `18.8.4` of `@types/node` leads to errors in implementations. Lock the version to `18.8.3`.

#### swagger-ui

Version `4.14.3` of `swagger-ui` leads to errors in implementations. Lock the version to `4.12.0`.


