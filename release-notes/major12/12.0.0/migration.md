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

* **Plugin action activity types**

  Scope: back-end

    1. **Step1**
       Locate all `@PluginAction` annotations in the implementation code.

    2. **Step2**
       Change parameter `activityTypes` to use the new type `com.ritense.processlink.domain.ActivityTypeWithEventName`.
       For example:
       ```kotlin
       @PluginAction(
           key = "send-email",
           title = "Send email",
           description = "Send an email with <example-product>.",
           activityTypes = [ActivityTypeWithEventName.SERVICE_TASK_START]
       )
       fun sendEmail(execution: DelegateExecution, emailProperties: EmailProperties) {
           ...
       ```

* **Removed form links module**

  Scope: back-end

  The `form-link` module was removed in favor of using the `process-link` module. The following changes should be made:

    1. **Migrate existing form links**

       Existing form link configurations should be migrated to process links. You can find a script to simplify this
       task [here](/using-valtimo/process-link/script/migrate-formlinks.sh).
    2. **Remove form link configuration files (optional)**

       Existing form link configuration files should be removed. This is optional as the files will just get ignored.
    3. **Remove existing tables (optional)**

       Existing form link configurations should be removed. This is optional as the tables technically do not have to
       be removed. Below is a changelog that removes the tables.
       
       ```xml
       <?xml version="1.1" encoding="UTF-8" standalone="no"?>
       <databaseChangeLog xmlns="http://www.liquibase.org/xml/ns/dbchangelog"
                          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                          xsi:schemaLocation="http://www.liquibase.org/xml/ns/dbchangelog http://www.liquibase.org/xml/ns/dbchangelog/dbchangelog-3.6.xsd">
           <changeSet author="Ritense" id="1">
               <dropAllForeignKeyConstraints baseTableName="process_form_association"/>
               <dropAllForeignKeyConstraints baseTableName="process_form_association_v2"/>
           </changeSet>
    
           <changeSet author="Ritense" id="2">
               <dropTable tableName="process_form_association"/>
               <dropTable tableName="process_form_association_v2"/>
           </changeSet>
       </databaseChangeLog>
       ```

* **Removed DocumentVariableDelegate class**
  
  Scope: back-end
  
  The `DocumentVariableDelegate` is replaced by the `DocumentDelegateService` class. As such, usages in processes and
  code should be updated to use `DocumentDelegateService` instead.

* **Deprecated code**

  Scope: back-end

  `CamundaProcessJsonSchemaDocumentService.getDocument(DelegateExecution execution)` has been deprecated. As such,
  usages in processes and code should be updated to use `DocumentDelegateService.getDocument(DelegateExecution)`
  instead.

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

  1. **Step1**

      Description
  2. **Step2**

      Description
