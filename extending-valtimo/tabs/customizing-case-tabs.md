# Customizing case tabs

On the detail page of a case instance, a number of tabs are shown. These tabs - and their order - can be customized
through the frontend code of an implementation.

## Modifying the tabs in the app module

To customize which tabs are shown, and in what order, open `app.module.ts` in the `src` folder of the implementation.
Here, a function `tabsFactory()` is defined. It provides a `Map` with tab IDs of type `string` and the corresponding
Angular component the tab needs to show. To customize the tabs shown for each case in the implementation, modify
the existing tabs provided by `tabsFactory()`, or add your own.

#### **`app.module.ts`**
```typescript
...
import {
    DefaultTabs, 
    DossierDetailTabAuditComponent,
    DossierDetailTabDocumentsComponent,
    DossierDetailTabProgressComponent,
    DossierDetailTabSummaryComponent,
    ...
} from '@valtimo/dossier';
// import the component used for the custom tab
import {MyCustomTabComponent} from './my-custom-tab.component.ts';
...

export function tabsFactory() {
    return new Map<string, object>([
        [DefaultTabs.summary, DossierDetailTabSummaryComponent],
        [DefaultTabs.progress, DossierDetailTabProgressComponent],
        [DefaultTabs.audit, DossierDetailTabAuditComponent],
        [DefaultTabs.documents, DossierDetailTabDocumentsComponent],
        // add the custom tab component with a string id to the tabsFactory()
        ['my-custom-tab', MyCustomTabComponent],
    ]);
}
```





