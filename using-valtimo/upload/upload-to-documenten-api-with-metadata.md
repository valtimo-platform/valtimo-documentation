# Uploading to Documenten API with metadata

The Documenten API is an API for storage and disclosure of documents and associated metadata. Valtimo supports uploading
files to the Documenten API with the option to input metadata through a dedicated tab on the detail page of a case
instance, or through a custom Form.IO component.

## Configuring the Documenten API tab

To enable the dedicated Documenten API tab in an implementation, set `uploadProvider` in the implementation's
environment file to `UploadProvider.DOCUMENTEN_API`. The documents tab on a case detail page will now show the
Documenten API uploader.

## Configuring the Documenten API Form.IO upload component

In order to make the Documenten API File Upload component available in Form.IO forms in your implementation, import
`registerDocumentenApiFormioUploadComponent` from `@valtimo/components` in your app module and move it into the
`AppModule` constructor like so:

#### **`app.module.ts`**
  ```typescript
...
import {
    ...
    registerDocumentenApiFormioUploadComponent,
} from '@valtimo/components';

...
export class AppModule {
    constructor(injector: Injector) {
        ...
        registerDocumentenApiFormioUploadComponent(injector);
    }
}
  ```

Afterwards, the component is available under the advanced section in the form builder.
