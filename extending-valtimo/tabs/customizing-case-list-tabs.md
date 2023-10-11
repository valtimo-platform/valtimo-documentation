# ⚠️**WARNING**⚠️

There is a new preferred way to configure case tabs. [Link](/using-valtimo/case/creating-case-tabs.md).

# Customizing case list tabs (deprecated)

On the case list page, three new tabs have been added to show the current state of the workload. These tabs - and 
their order - can be customized through the frontend code of an implementation.

## Modifying the tabs in environment file

To customize which tabs are displayed and in what order, you will need to configure this in the `environment` file.

Here, the `ValtimoConfig` property is defined, and within it, it is possible to declare in the `visibleDossierListTabs` property the tabs you want to show and what order they should be displayed in.

### Example:
```typescript
export const environment: ValtimoConfig = {
    ...,
    visibleDossierListTabs: [DossierListTab.MINE, DossierListTab.OPEN, DossierListTab.ALL]
}
```





