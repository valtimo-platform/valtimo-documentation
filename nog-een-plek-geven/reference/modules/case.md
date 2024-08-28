# 🛑 Case

## Case tabs types

The following case types are supported by Valtimo.

<table><thead><tr><th width="192">Type</th><th width="181">Type key</th><th>Description</th></tr></thead><tbody><tr><td><strong>Standard</strong></td><td>standard</td><td>A collection of tabs is available that support different Valtimo features. The tabs that are available are listed below.</td></tr><tr><td><strong>Form.io form</strong></td><td>formio</td><td>Form.io tabs can be configured to show a Form.io form.</td></tr><tr><td><strong>Custom</strong></td><td>custom</td><td>Custom tabs can be configured to show a custom Angular component.</td></tr></tbody></table>

### Standard tabs

<table><thead><tr><th width="192">Type</th><th width="180">Type key</th><th>Description</th></tr></thead><tbody><tr><td><strong>Summary</strong></td><td>summary</td><td>Shows a single Form.io form with the name: '.summary'.</td></tr><tr><td><strong>Progress</strong></td><td>progress</td><td>Shows a BPMN model with the progress of the case.</td></tr><tr><td><strong>Audit</strong></td><td>audit</td><td>Shows the audit logging for the case.</td></tr><tr><td><strong>Documents</strong></td><td>documents</td><td>Shows all files and documents that are associated with the case.</td></tr><tr><td><strong>Contact-moments</strong></td><td>contact-moments</td><td>Shows all contact moments with a client that are registered in the <a href="https://vng-realisatie.github.io/gemma-zaken/standaard/contactmomenten/index">contactmomenten API</a>.</td></tr><tr><td><strong>Zaakobjecten</strong></td><td>zaakobjecten</td><td>Shows all 'zaak' objects of a case.</td></tr><tr><td><strong>Notes</strong></td><td>notes</td><td>Allows case workers to add and read notes for the case.</td></tr></tbody></table>

### Default case tabs

By default, each new case is given the following standard tabs:

* Summary
* Progress
* Audit
* Documents
* Notes
