# Exporting and importing case definitions

A case definition is a collection of configurations and definitions, such as the document definition, process
definitions, forms, form flows and process links. These case definitions can be exported as a ZIP archive, so it can
be imported via the UI, added to the repository or shared with others.

## Export

Exporting can be done by navigating to the case definition detail page. This will result in a ZIP archive containing 
configurations and definitions that make up the case definition. The structure is the same as found in any application
that makes use of the auto-deployment offered by Valtimo.

![Exporting a case definition](img/export-case-definition.png)

### Excluded from the export

Some related configurations are not exported, as they are not case definition specific. These are:
- Dashboards
- Access control
- Plugin configurations