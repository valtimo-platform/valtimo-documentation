# Customizing case list tabs

On the case list page, three new tabs have been added to show the current state of the workload. These tabs - and 
their order - can be customized through the frontend code of an implementation.

## Modifying the tabs in environment.ts

To customize which tabs are displayed and in what order, you will need to configure this in the `environment.ts` file.

Here, the `ValtimoConfig` property is defined, and within it, it is possible to declare in the `visibleDossierListTabs` property the tabs you want to show and display them in the order that is inserted in this property.

#### **`environment.ts`**
```typescript
export const environment: ValtimoConfig = {
    ...,
    visibleDossierListTabs: [DossierListTab.MINE, DossierListTab.OPEN, DossierListTab.ALL]
}
```





