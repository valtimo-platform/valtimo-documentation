# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Spring boot 3 upgrade**

  Scope: back-end

  Full migration instructions for this change can be found [here](spring-boot3-migration.md).

* **Valtimo dependencies**

  Scope: back-end

  `valtimo-dependencies` and `valtimo-gzac-depenencies` should no longer be used for `dependencyManagement` or `platform`.
  This functionality has been replaced by [valtimo-dependency-versions](../../../getting-started/modules/core/valtimo-dependency-versions.md).

* **Access control files**

  Scope: back-end

    1. **Step1**

       Locate all files in the backend libraries matching: `/resources/config/<filepath>/<filename>.permission.json`
    2. **Step2**
       Locate all permissions for `CamundaTask` that use the `assignee` field. For example:
       ```json
       {
           "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
           "action": ...,
           "conditions": [
               {
                   "type": "field",
                   "field": "assignee",
                   "operator": "==",
                   "value": "${currentUserEmail}"
               }
           ]
       }
       ```

    3. **Step3**
       Change `${currentUserEmail}` to `${currentUserId}`.

       If the `value` field contains an actual email, then the email must be changed to a user ID.

* **Access control database**

  Scope: back-end

    1. **Step1**

       Go to the 'Admin' menu item and then to 'Access control'. Then for every role, do the steps below.

    2. **Step2**
       Locate all permissions for `CamundaTask` that use the `assignee` field. For example:
       ```json
       {
           "resourceType": "com.ritense.valtimo.camunda.domain.CamundaTask",
           "action": ...,
           "conditions": [
               {
                   "type": "field",
                   "field": "assignee",
                   "operator": "==",
                   "value": "${currentUserEmail}"
               }
           ]
       }
       ```

    3. **Step3**
       Change `${currentUserEmail}` to `${currentUserId}`

       If the `value` field contains an actual email, then the email must be changed to a user ID.

* **Value resolvers**

  Scope: back-end

    1. **Step1**
       Locate all Kotlin classes that extend the `: ValueResolverFactory` interface in the implementation code.

    2. **Step2**
       In the classes found, locate all function with name `handleValues(...)`

    3. **Step 3**
       Change the type of parameter `values` from: `Map<String, Any>` to also support null values: `Map<String, Any?>`.

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

      Description
  2. **Step2**

      Description
