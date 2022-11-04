# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Java 17**
    
    Scope: Backend
    
    In order to run Valtimo a Java 17 environment must be used. The way to configure this is different per implementation.
    For example, the Java version used when gradle with gradle can be set like this:
    
    ```groovy
    sourceCompatibility = JavaVersion.VERSION_17
    targetCompatibility = JavaVersion.VERSION_17
    ```
    
    Also make sure that when building to a docker container a base image is used that supports Java 17.

* **Angular upgrade**

  Scope: Frontend

    In order to use the new front-end libraries based on Angular version 14 in an implementation, run the following
    command in the root of the implementation project:
    `ng update @angular/core@14 @angular/cli@14`

* **Dependency upgrades**

  Scope: Frontend

    In order to use the front-end libraries with upgraded dependencies, make sure to first upgrade your implementation
    to Angular 14 by following the steps mentioned on this page.

* **Redundant stylesheets**

    Next, you might have to delete the following lines from the `styles` array in `angular.json` in the root of your
    implementation:

    `"node_modules/dmn-js/dist/assets/dmn-font/css/animation.css"`

    `"node_modules/dmn-js/dist/assets/dmn-font/css/dmn-ie7.css"`

    `"node_modules/dmn-js/dist/assets/dmn-font/css/dmn-ie7-codes.css"`

* **Matching dependencies**

    Then, make sure the following dependencies in `package.json` in the root of your implementation have the following
    versions:

    #### **`package.json`**

    ```json
    {
      "dependencies": {
        ...
        "@auth0/angular-jwt": "^5.0.1",
        "@mdi/font": "^7.0.96",
        ...
        "dmn-js": "^12.1.0",
        "dropzone": "^6.0.0-beta.2",
        "ngx-color-picker": "^13.0.0",
        ...
        "ngx-translate-multi-http-loader": "^9.0.0",
        ...
        "swagger-ui": "^4.15.0",
        ...
        "zone.js": "^0.11.8"
      },
      "devDependencies": {
        ...
        "@types/jasmine": "^4.3.0",
        "@types/jasminewd2": "^2.0.10",
        ...
        "jasmine-core": "^4.4.0",
      } 
    }
    ```
  
    Note: if your implementation has any dependencies not included in the above example, and installing dependencies
    or building your application causes errors, make sure the versions of these dependencies match the versions
    in this release of `valtimo-frontend-libraries`.

    *Translate loader upgrade*

    `ngx-translate-multi-http-loader` has been upgraded from version 7 to version 9. This upgrade requires adjustments 
    in implementations of Valtimo: `HttpClient` needs to be replaced by `HttpBackend` in the `deps` of the `loader` of 
    `TranslateModule`.

    #### **`app.module.ts.ts`**

    ```typescript
    import {HttpBackend, HttpClientModule} from '@angular/common/http';
    ...
  
    @NgModule({
      ...
      imports: [
        ...
        TranslateModule.forRoot({
          loader: {
             provide: TranslateLoader,
             useFactory: MultiTranslateHttpLoaderFactory,
             deps: [HttpBackend, ConfigService],
          },
        }),
      ],
      ...
    })
    ...
    ```
    If your implementation uses custom translation resources, these need to be adjusted in the environment file
    of your implementation. The environment property `translationResources` no longer accepts an array of
    `ITranslationResource`, but an array of strings. The properties `prefix` and `suffix` are now redundant. For
    example, if the previous value in your environment file was `[{prefix: 'src/assets/translation', suffix: 'json'}]`,
    it should now be `['src/assets/translation']`.

    *Migrating from `Protractor` to `Cypress`*

    Support for `Protractor` (an end-to-end testing framework) in the Angular CLI will be discontinued. Either remove
    `Protractor` from your implementation, or migrate to Cypress [by following this guide](https://blog.ninja-squad.com/2021/05/05/migrating-from-protractor-to-cypress/).
    The latter is recommended.
    
