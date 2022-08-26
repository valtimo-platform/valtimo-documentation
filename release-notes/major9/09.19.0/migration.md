# Migration

This page describes how to update Valtimo from the previous to this version.

* **Form flow `onBack` property is null for existing records**

  If you were using form flow before, any existing form definitions will no longer work. A Liquibase 
  changeset should be added that updates all existing records in the `form_flow_step` table. Specifically, the newly
  added `onBack` property (of type JSON) needs to be set to an empty array.

* **Breaking change 2/Deprecation 2**

  1. **Step1**

      Description
  2. **Step2**

      Description
