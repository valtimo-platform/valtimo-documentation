# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Add fix for custom Form.io components not rendering consistently**

    Scope: front-end
    
    To circumvent custom Form.io components not rendering in certain situations, imports `enableCustomFormioComponents`
    from `@valtimo/components` in the `app.module.ts` file of your implementation. Next, call this function at the top
    of the constructor of `AppModule` like so:


```typescript
...
import {
    enableCustomFormioComponents,
} from '@valtimo/components';
...

...
export class AppModule {
    constructor(injector: Injector) {
        // make sure this function is called before custom component registration functions
        enableCustomFormioComponents(injector);
        
        registerFormioUploadComponent(injector);
        registerDocumentenApiFormioUploadComponent(injector);
    }
}
```
