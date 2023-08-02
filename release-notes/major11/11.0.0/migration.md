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

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

     Description

  2. **Step2**

     Description
