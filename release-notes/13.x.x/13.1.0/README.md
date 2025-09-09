# 13.1.0

## New Features

#### Case definition list columns and search fields

List columns and search fields can now be configured via a JSON Editor under the Case definition details.

#### Dashboards widget configuration

Dashboard widget configurationscan now be edited via a JSON Editor under the dashboard details.

<details>

<summary>GZAC edition</summary>

#### New Zaken API plugin actions

New actions have been added to the Zaken API plugin:

##### Patch zaak

The Patch zaak action allows partial updates to a Zaak. Only the fields that are set while configuring the action 
will be updated.

##### New create zaakrol types

New actions were added to create a <em>ZaakRol</em> of different types. Before it was possible to create a 
<em>ZaakRol</em> where the type of <em>betrokkene</em> was `natuurlijk_persoon` and `niet_natuurlijk_persoon` only. 
The following actions were added to create a <em>ZaakRol</em> of the respective type:
- Create zaakrol - employee (for `medewerker`)
- Create zaakrol - organizational unit (for `organisatorische_eenheid`)
- Create zaakrol - branch (for `vestiging`)

</details>

## Enhancements

#### Task sub titles

The sub title of a task is now also displayed to users that do not have permission to view the task itself.

#### Docker Compose support for local development

Improved support for running Valtimo locally using Docker Compose. Configuring references to localhost will no 
longer break when running other related ZGW services in Docker containers.

#### Improved context support in access control

Added a NoContext option to the access control configuration. This allows for configuring access control for instances 
where no context is provided. For example, when starting a supporting process, the case is provided as context. However, 
when starting a case, no context is provided. With the NoContext option, it is now possible to configure access control
for starting a case, without giving users permissions for starting any supporting processes.

#### Sorted object types in the main menu

Object types in the main menu when using object management are now sorted alphabetically by name.
