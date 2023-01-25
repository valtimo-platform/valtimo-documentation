# Modal

Valtimo uses the IBM modals from the `angular-carbon` library. 

## Creating a modal

A Modal is a component that extends the `BaseModal` class. A minimal modal looks like this
```typescript
import {Component} from '@angular/core';
import {BaseModal} from 'carbon-components-angular/modal';

@Component({
  selector: 'valtimo-new-modal',
  templateUrl: './new-modal.component.html',
  styleUrls: ['./new-modal.component.scss'],
})
export class NewModalComponent extends BaseModal {
    
}
```
Along with the following html for `./new-modal.component.html`
```html
<ibm-modal [open]="open" (overlaySelected)="closeModal()">
  <ibm-modal-header (closeSelect)="closeModal()">{{
    'newModal.title' | translate
  }}</ibm-modal-header>
  <section class="bx--modal-content p-2">
  </section>
  <ibm-modal-footer>
    <button class="bx--btn bx--btn--secondary" (click)="closeModal()">
      {{ 'interface.cancel' | translate }}
    </button>
  </ibm-modal-footer>
</ibm-modal>
```
In order to present the modal, another controller must have the `ModalService` from the `carbon-components-angular` injected
and call the following method
```typescript
this.modalService.create({
  component: NewModalComponent
});
```

## Passing data to a modal

Using the `@Inject` annotation, parameters can be passed from the calling controller to the modal when it is being created.
For instance, a modal that shows a custom label, is created like this in the controller.
```typescript
this.modalService.create({
  component: NewModalComponent,
  inputs: {
    messageToShow: "hello world",
  },
});
```
Then the constructor of the modal gets a new parameter with the `@Inject` annotation
```typescript
export class NewModalComponent extends BaseModal {
  
    constructor(
        @Inject('formToDuplicate') public messageToShow: String
    ) {
        super();
    }
}
```
Which is then shown in the HTML
```html
<ibm-modal [open]="open" (overlaySelected)="closeModal()">
  <ibm-modal-header (closeSelect)="closeModal()">{{
    'newModal.title' | translate
  }}</ibm-modal-header>
  <section class="bx--modal-content p-2">
    {{messageToShow}}
  </section>
  <ibm-modal-footer>
    <button class="bx--btn bx--btn--secondary" (click)="closeModal()">
      {{ 'interface.cancel' | translate }}
    </button>
  </ibm-modal-footer>
</ibm-modal>
```