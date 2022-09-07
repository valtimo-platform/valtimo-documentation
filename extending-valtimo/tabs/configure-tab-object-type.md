# Setting extra tabs for Zaak object type

On the details page of a case instance, several tabs are shown, including the Zaakobject tab.
It is possible to configure to display the guides by zaak object type, so the user can see all relevant data in 
a separate tab.

These tabs can be customized via front-end implementation code.

## Configuring the tabs in the environment file

To customize which tabs are shown, open `environment.ts` in the implementation's `src/environment` folder.
Here, the `caseObjectTypes` object is defined. It can provide a list of definition names, that contain one or more 
objects names of types of type `string`, that will be converted into new tabs to be displayed.

Configuration is optional (see example below).

#### **`environment.ts`**

  ```typescript
  export const environment: ValtimoConfig = { ...
    caseObjectTypes: {
      leningen: ['Boom', 'Straatverlichting']
    },
   }
  ```

Per configured Zaakobjecttype, a separate new tab will show at the case detail page, with a list of object type.
This list will be populated with the following data: `index`, `registration at`, `title` and a 
**'view object'** `button` to display the task details.

By clicking on the button, a modal will be opened on the right side of the page showing a Formio pre-filled with the information and details
of this object. These data are readonly.
If there is no return from the list of data or information in the modal, a helpful message will be displayed 
stating that the data was not found.

