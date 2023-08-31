# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Change in Recipient.Type values**

  Scope: back-end

  To meet coding standards, the Enum values of ```com.ritense.valtimo.contract.mail.model.value.Recipient.Type``` have been changed to all uppercase.
  References to these Enum values should be changed in implementations:
    - Change uses of Type.To to Type.TO
    - Change uses of Type.Cc to Type.CC
    - Change uses of Type.Bcc to Type.BCC

* **Rename application property valtimo.jwt.secret**

  Scope: back-end

    1. **Find valtimo.jwt.secret**

       Find all occurrences of `valtimo.jwt.secret` and rename them all to `valtimo.oauth.public-key`. This property is
       usually found in the `application.yml`.

    2. **Find `VALTIMO_JWT_SECRET`**

       Find all occurrences of `VALTIMO_JWT_SECRET` and rename them to `VALTIMO_OAUTH_PUBLIC_KEY`. This environment
       variable can potentially be found in many different places such as:
        - `.env.properties` file inside the repository
        - AWS Parameter store
        - Kubernetes `.yaml` file

* **Rename application property valtimo.jwt.tokenValidityInSeconds**

  Scope: back-end

    1. **Find valtimo.jwt.tokenValidityInSeconds**

       Find all occurrences of `valtimo.jwt.tokenValidityInSeconds` and rename them all
       to `valtimo.oauth.tokenValidityInSeconds`. This property is usually found in the `application.yml`.

    2. **Find `VALTIMO_JWT_TOKEN_VALIDITY_IN_SECONDS`**

       Find all occurrences of `VALTIMO_JWT_TOKEN_VALIDITY_IN_SECONDS` and rename them
       to `VALTIMO_OAUTH_TOKEN_VALIDITY_IN_SECONDS`. This environment variable can potentially be found in many
       different places such as:
        - `.env.properties` file inside the repository
        - AWS Parameter store
        - Kubernetes `.yaml` file

* **Change in Carbon Design System version**

  Scope: front-end

  1.  **Install new Carbon Dependencies**

      - Delete node_modules.
      - Run 'npm install --legacy-peer-deps'.

  2.  **Update all carbon selectors from 'ibm' to 'cds'**

      #### **`Tags`**:

          Deprecated:
          <ibm-placeholder></ibm-placeholder>

          Active:
          <cds-placeholder></cds-placeholder>

      #### **`Directives`**:

          Deprecated:
          <button ibmButton="primary"></button>

          Active:
          <button cdsButton="primary"></button>

      #### **`Classes`**:

          Deprecated:
          <svg class="ibm--btn__icon"></svg>

          Active:
          <svg class="cds--btn__icon"></svg>

  3.  **Remove all usages of @carbon/icons-angular**

      #### **`Icon`**:
          Deprecated:
          <svg class="ibm--btn__icon" ibmIconArrowDown size="16"></svg>

          Active:
          <svg class="cds--btn__icon" cdsIcon="arrow--down" size="16"></svg>

  3.  **Registering @carbon/icons**

    - In order to use @carbon/icons, the IconModule needs to be imported.

      #### **`sample.module.ts`**
      ````typescript
      ...
      // import IconModule
      import {IconModule} from 'carbon-components-angular';
      ...

      @NgModule({
          ...
          imports: [
            ...
            IconModule
            ...
          ]
          ...
      })
      export class SampleModule {
       ...
      }
      ````
    - Some icons may not be available by default, so they need to be registered in the component where they are needed. This is accomplished via the Carbon IconService
      #### **`sample.component.ts`**
      ````typescript
      ...
      // import IconService
      import {IconService} from 'carbon-components-angular';
      ...
      // import Icons
      import {ArrowDown16, ArrowUp16} from '@carbon/icons';
      ...

      @Component({
          ...
      })
      export class SampleComponent implements OnInit{
       ...
       constructor(private readonly iconService: IconService) {}
       ...
       public ngOnInit(): void {
        this.iconService.registerAll([ArrowDown16, ArrowUp16]);
       }
       ...
      }
      ````
    - All icons available through the Carbon library can be found [here](https://angular.carbondesignsystem.com/?path=/docs/components-icon--docs)

* **Remove 'Context' admin menu**

  Scope: front-end

    1. **Remove @valtimo/context**

        - Remove `@valtimo/context` library from the `package.json`.
        - Remove `ContextModule` module from the `app.module.ts`.

    2. **Remove @valtimo/management**

        - Remove `@valtimo/management` library from the `package.json`.
        - Remove `ManagementContextModule` module from the `app.module.ts`.
        - Remove the `Contexts` link from the `environment.ts`

* **Update connector and plugin keys**

  Scope: back-end/front-end

  In order for keys to be encrypted with GCM (as apposed to ECB, see
  [here](valtimo-backend-libraries.md#new-features) for more information), all existing plugin configurations need
  to be updated.

  1. **Save existing connector configurations with their keys**
  2. **Save plugin configurations with their keys**
  3. **See if encryption is used anywhere else in the application**

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

      Description
  2. **Step2**

      Description
