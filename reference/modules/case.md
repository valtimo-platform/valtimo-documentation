# Case

## Case tabs types

The following case types are supported by Valtimo.

| Type         | Type key | Description                                                                                                              |
|--------------|----------|:-------------------------------------------------------------------------------------------------------------------------|
| **Standard** | standard | A collection of tabs is available that support different Valtimo features. The tabs that are available are listed below. |
| **Form.io**  | formio   | Form.io tabs can be configured to show a form.io form.                                                                   |
| **Custom**   | custom   | Custom tabs can be configured to show a custom Angular component.                                                        |


### Standard tabs

| Type                | Type key        | Description                                                                                                                                                             |
|---------------------|-----------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Summary**         | summary         | Shows a single form.io form with the name: '<case-key>.summary'.                                                                                                        |
| **Progress**        | progress        | Shows a BPMN model with the progress of the case.                                                                                                                       |
| **Audit**           | audit           | Shows the audit logging for the case.                                                                                                                                   |
| **Documents**       | documents       | Shows all files and documents that are associated with the case.                                                                                                        |
| **Contact-moments** | contact-moments | Shows all contact moments with a client that are registered in the [contactmomenten API](https://vng-realisatie.github.io/gemma-zaken/standaard/contactmomenten/index). |
| **Zaakobjecten**    | zaakobjecten    | Shows all 'zaak' objects of a case.                                                                                                                                     |
| **Notes**           | notes           | Allows case workers to add and read notes for the case.                                                                                                                 |

### Default case tabs

By default, each case is given the following standard tabs:
- Summary
- Progress
- Audit
- Documents
- Notes
