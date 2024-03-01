# Pending Changes mechanism

The PendingChanges mechanism is meant to prevent data loss when navigating away from a page with unsaved changes.

![Example of PendingChanges modal](img/pending-changes-modal.png)

In order for the mechanism to work, both the routing module and the component for which to apply it need to be configured.

## Configuring your Router:

Router needs to be configured to accept cancelling navigation.

#### **`example-routing.module.ts`**

```typescript
...
// import Router
import { Router } from '@angular/router';
...
// import RouterUtils from @valtimo
import {RouterUtils} from '@valtimo/config';
...
// import PendingChangesGuard from @valtimo
import {pendingChangesGuard} from '@valtimo/components';
...

// apply guard to routes
...
    const routes: Routes = [
      ...
      {
        ...,
        path: 'example-path',
        component: 'example-component',
        canDeactivate: [pendingChangesGuard]
        ....
      }
      ...
    ]
...
export class ExampleRoutingModule {
    ...
    constructor(private router: Router) {
      RouterUtils.configureRouter(this.router)
    }
}
```

## Configuring your component

Any component that needs to use the mechanism needs to tell it when to be triggered and when not to.

#### **`example.component.ts`**

```typescript
...
// import PendingChangesComponent from @valtimo
import { PendingChangesComponent } from '@valtimo/components';

...
//import modalService and translateService for the Modal to work
import {ModalService} from 'carbon-components-angular';
import {TranslateService} from '@ngx-translate/core';
...

...
// Make the component targetable by the PendingChanges guard
export class ExampleComponent extends PendingChangesComponent {
    ...
    // initialize PendingChangesComponent
    constructor(
      private modalService: ModalService,
      private translateService: TranslateService
    ) {
      super(modalService, translateService)
    }
    ...

    ...
    // let the component know the guard needs to be triggered
    public exampleDoChange(): void {
      //pendingChanges is an attribute of the PendingChangesComponent that lets it know the guard might need to be triggered
      this.pendingChanges = true;
      ...
    }

    ...
    // let the component know the changes have been saved
    public exampleSaveChanges(): void {
      ...
      this.pendingChanges = false;
    }
    ...
}
```

## Custom handlers when closing the PendingChanges modal

In case custom handlers need to be added when selecting either _Confirm_ or _Cancel_, the PendingChangesComponent has two _protected_ methods that can be overwritten for that purpose.

#### **`pending-changes.component.ts`**

```typescript
...
  protected onCancelRedirect(): void {}

  protected onConfirmRedirect(): void {}
...
```

When overwriting these method, the logic inside of them gets triggered right before closing the modal.

#### **`example.component.ts`**

```typescript
...
// import PendingChangesComponent from @valtimo
import { PendingChangesComponent } from '@valtimo/components';

...
//import modalService and translateService for the Modal to work
import {ModalService} from 'carbon-components-angular';
import {TranslateService} from '@ngx-translate/core';
...

...
// Make the component targetable by the PendingChanges guard
export class ExampleComponent extends PendingChangesComponent {
    ...
    // initialize PendingChangesComponent
    constructor(
      private modalService: ModalService,
      private translateService: TranslateService
    ) {
      super(modalService, translateService)
    }
    ...

    ...
    // overwrite onCancelRedirect method
    protected onCancelRedirect(): void {
      //custom logic for canceling of navigation
    }
    ...
}
```

## Configuring a custom pending changes modal

In case a different modal needs to be displayed instead of the default PendingChanges confirmation, this can be achieved through the following property and by making use of the following methods.

#### **`pending-changes.component.ts`**

```typescript
...
  protected customModal: any = null;

  protected onCustomCancel(): void {
    this._activeModal = null;
    this.deactivateSubject.next(false);
    this.onCancelRedirect();
  }

  protected onCustomConfirm(): void {
    this._activeModal = null;
    this.deactivateSubject.next(true);
    this.onConfirmRedirect();
  }
...
```

In order to set the custom modal, your component needs to be implemented like this:

#### **`example.component.ts`**

```typescript
...
// import AfterViewInit and ViewChild to load your custom modal
import { AfterViewInit, ViewChild } from '@angular/core';
// import PendingChangesComponent from @valtimo
import { PendingChangesComponent } from '@valtimo/components';

...
// Make the component targetable by the PendingChanges guard
export class ExampleComponent extends PendingChangesComponent implements AfterViewInit {
    ...
    // CustomModalComponent is the modal you'd like to display instead of the default pending-changes modal
    @ViewChild(CustomModalComponent) modalComponent;
    ...
    // assign your custom modal
    public ngAfterViewInit(): void {
      // customModal field is protected from the PendingChangesComponent
      this.customModal = this.modalComponent
    }
    ...
    // method in your component that is called when redirecting is confirmed
    public onConfirmClick(): void {
      // method from the PendingChangesComponent in order to let the guard know that the redirect can happen
      this.onCustomConfirm();
    }

    // method in your component that is called when redirecting is canceled
    public onCancelClick(): void {
      // method from the PendingChangesComponent in order to let the guard know that the redirect is not allowed
      this.onCustomCancel();
    }
    ...
}
```
