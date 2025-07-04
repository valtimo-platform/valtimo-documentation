# 12.10.0

## New features

#### Hiding locked tasks from the tasklist

The task list now supports filtering out locked tasks. Using this filter, users will only see the tasks in the list where they have access to (`view` permission on the task).

#### Store nested properties in process variables

Nested properties submitted via Formio forms using process variables (e.g. `pv.aanvrager.voornaam`) are now stored correctly as structured objects in Camunda process variables. Previously, each nested field was saved as a separate flat variable, leading to incorrect data handling.

<details>

<summary>GZAC edition</summary>

#### Change metadata for Documenten API documents with status 'definitive'

Documenten API documents can now be changed. When documents have status 'definitive', a new version of the document is created for metadata changes. The content of the document can't be changed.

Editing document metadata is only allowed when the user has the correct permissions. More information can be found [here](broken-reference).

#### Retrieve Eigenschappen via Catalogi API plugin

The Catalogi API plugin has been extended to retrieve Eigenschappen (definition) based on the name. These Eigenschappen can now be stored as process variables and can be used to create a new Zaakeigenschap without differences between OTAP-environments.

</details>

## Bugfixes

* Nested property paths in Formio components (e.g. paths containing arrays or expressions like `/favorites/{indexOf(...)}`) were not handled correctly.
* On the 'logs' page, the 'edit' button was incorrectly visible when navigating from the case widget page.

<details>

<summary>GZAC edition</summary>

* Upload Documenten API documents in parts now uses the correct lock property
* Documenten API file upload components now work correctly when used in a Form.io editgrid.

</details>

## For developers

* The ZGW API clients now support running the ZGW services in Docker. Connections to `localhost` will be rewritten to `host.docker.internal` . This behaviour can be enabled by setting the `valtimo.docker.filter.enabled`  application property to true.
