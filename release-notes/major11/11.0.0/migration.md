# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Change in Recipient.Type values**

  Scope: back-end

  To meet coding standards, the Enum values of ```com.ritense.valtimo.contract.mail.model.value.Recipient.Type``` have been changed to all uppercase.
  References to these Enum values should be changed in implementations:
    - Change uses of Type.To to Type.TO
    - Change uses of Type.Cc to Type.CC
    - Change uses of Type.Bcc to Type.BCC

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

      Description
  2. **Step2**

      Description
