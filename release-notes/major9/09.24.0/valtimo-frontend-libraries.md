# Frontend libraries 5.13.0 (RC)

## New Features

The following features were added:

* **Added link to assign assignee to case**

  On the case details page, a button has been added to the header to add, change, or remove a case assignee.
  
  A drop-down list with the names of all available candidates will be displayed when clicking on this button. The 
  selected candidate will be assigned to the case, and shown in the header.
  
  To unassign an assignee from a case, click on the 'remove' button present next to the label with the name.

* **Default Language Setting**

  A new (optional) environment property `langKey` has been added to set the default language. The new property is an enum and includes the following values: `Language.NL`, `Language.EN` and `Language.DE`.

  The default language is used for every user that has not set a preferred language. If no language is set in the `environment.ts` the default is set to `Language.NL`.

* **Valtimo list action callback**

  A new `$event` parameter has been added to the action callback from the valtimo list component. 

  You can use this parameter to call `$event.stopPropagation()` to stop the row click listener being triggered when using actions.

  <details>
    <summary>Code Example</summary>

    Imagine that you have a `<valtimo-list>` set up like this to display orders.

    ```angular2html
    <valtimo-list
        [items]="orders"
        [fields]="ordersFields"
        (rowClicked)="orderClick($event)"
        [actions] = "ordersActions"
    ></valtimo-list>
    ```
  
    In the controller, you should have something like this

    ```typescript
    public ordersActions: any[] = [{
        "columnName": "Delete",
        "iconClass": "icon mdi mdi-close",
        "callback": this.deleteOrder
    }]
  
    public orderClick(order) {
        this.router.navigateByUrl("/dossiers/"+order.definitionId.name+"/document/"+order.id+"/summary");
    }

    public deleteOrder(row: any) {
        this.deleteService().showDeleteConfirmation(row);
    }
    ``` 
  
    This will not work, because when you press the `"Delete"` action, it will not only trigger the `deleteOrder` method, but afterwards will also trigger the `orderClick` method. 
    This means that you will navigate to the case, while you were trying to delete it.
  
    To get around this, we can now use the extra `$event` parameter to call `$event.stopPropagation()` in the action callback. This will prevent any other click listeners from being triggered, including the `orderClick` method.
  
    ```typescript
    public deleteOrder(row: any, $event: MouseEvent) {
        this.deleteService().showDeleteConfirmation(row);
        $event.stopPropagation(); 
    }
    ```
  </details>

## Bugfixes

No bugfixes.

## Breaking changes

No breaking changes.

## Deprecations

No new deprecations.

## Known issues

No new known issues.
