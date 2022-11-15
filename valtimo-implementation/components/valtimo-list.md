# Valtimo list

The valtimo list is a component to make building lists faster and easier. 

## Setting up a simple list

Let's begin by creating a simple list which doesn't do anything for now besides display some data. 
Assuming you already have a project, find the html page you want to add the list to and add the following html

```angular2html
<valtimo-list
    [items]="items"
    [fields]="itemFields"
></valtimo-list>
```

Next, in the controller, add the following code

```typescript
public items: Array<any>;
public itemFields = [
{
    key: 'id',
    label: 'ID',
},
{
    key: 'nested.name',
    label: 'Name',
}
];

ngOnInit() {
    this.items = [ 
        { 
            id: 1, 
            nested: { name: "one" }
        }, {
            id: 2,
            nested: { name: "two"}
        }];
}
```

This will create a simple list that shows our two items. 

![simple-list.png](simple-list.png)

## Clicking on rows

If you want some action to happen when the user clicks on a row, you can use the `(rowClicked)` property like so.

Change your html to add the property
```angular2html
<valtimo-list
    [items]="items"
    [fields]="itemFields"
    (rowClicked)="onItemClicked($event)"
></valtimo-list>
```

Add the following to your controller
```typescript
public itemClicked(item) {
    this.router.navigateByUrl("/items/"+item.id);
}
```

## Adding actions

If you want clickable icons in the list, you can use the `[actions]` property.

Change your html to add the property
```angular2html
<valtimo-list
    [items]="items"
    [fields]="itemFields"
    [actions]="itemActions"
></valtimo-list>
```

Then add the following to your controller
```typescript
public readonly itemActions: any[] = [{
  'columnName': 'delete',
  'iconClass': 'icon mdi mdi-close',
  'callback': this.deleteItem.bind(this)
}];

public deleteItem(item, $event) {
    const index = this.items.indexOf(item, 0);
    if (index > -1) {
        this.items.splice(index, 1); //remove item
    }
    
    $event.stopPropagation();
}
```

Note the `$event.stopPropagation()`, this stops any other click listeners from being triggered. Without this line the clickListener from the previous chapter would also run.

![actions.png](actions.png)