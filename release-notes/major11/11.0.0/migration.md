# Migration

This page describes how to update Valtimo from the previous version to the current.

- **Change in Recipient.Type values**

  Scope: back-end

  To meet coding standards, the Enum values of `com.ritense.valtimo.contract.mail.model.value.Recipient.Type` have been changed to all uppercase.
  References to these Enum values should be changed in implementations:

  - Change uses of Type.To to Type.TO
  - Change uses of Type.Cc to Type.CC
  - Change uses of Type.Bcc to Type.BCC

- **Change in Carbon Design System version**

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


* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

     Description

  2. **Step2**

     Description
