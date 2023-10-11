# Case

## Case tabs types

The access to the following resources is limited by Valtimo access control.

| Type         | Type name | Description                                                                     |
|--------------|-----------|:--------------------------------------------------------------------------------|
| **Standard** | standard  | Valtimo is shipped with a few standard tabs that do not need any configuration. |
| **Form.io**  | formio    | The form.io tab can be configured to show any form.io form.                     |
| **Custom**   | custom    | The custom tab can be configured to show a custom Angular component.            |


### Standard tabs

| Type                | Type name       | Description                                                                                                                                                             |
|---------------------|-----------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Summary**         | summary         | Shows a single form.io form with the name: '<case-key>.summary'.                                                                                                        |
| **Progress**        | progress        | Shows a BPMN model with the progress of the case.                                                                                                                       |
| **Audit**           | audit           | Shows the audit logging for the case.                                                                                                                                   |
| **Documents**       | documents       | Shows all files and documents that are associated with the case.                                                                                                        |
| **Contact-moments** | contact-moments | Shows all contact moments with a client that are registered in the [contactmomenten API](https://vng-realisatie.github.io/gemma-zaken/standaard/contactmomenten/index). |
| **Zaakobjecten**    | zaakobjecten    | Shows all 'zaak' objects of a case.                                                                                                                                     |
| **Notes**           | notes           | Shows all notes of all case workers that worked on the case.                                                                                                            |

### Default case tabs

By default, each case is given the following standard tabs:
- Summary
- Progress
- Audit
- Documents
- Notes
