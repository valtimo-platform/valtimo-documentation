# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Migrate form process 'Retrieve Document and link to Zaak' to process 'Link document to zaak'**

  Scope: front-end

    1. **Step1**

       Under the 'Admin' menu, go to the 'Process links' menu.
    2. **Step2**

       Select process 'Retrieve Document and link to Zaak'.
    3. **Step3**

       Click the service task 'Link Document to Zaak' and write down all properties of the process link. If no process
       link is configured, migrating is not necessary.
    4. **Step4**

       Now select the process 'Process PortaalTaak Uploaded Documents'.
    5. **Step5**

       Click the service task 'Link Document to Zaak' and configure the process link as was written down.
    6. **Step6**

       (Optional) You may now delete the process 'Retrieve Document and link to Zaak'. Unfortunately, Valtimo doesn't
       provide a simple way of deleting a process definition.