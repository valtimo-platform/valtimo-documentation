# Custom case headers

Instead of de default case header which only shows a case name, each case header can be customized, using a
configuration in the environment file of a front-end implementation.

The custom header consists of blocks that use the Bootstrap column classes to define the block sizes. In this way, any
layout can be created.

| <!-- -->                                          |
|---------------------------------------------------|
| ![Custom case header](img/custom-case-header.png) |
| <center>A custom case header</center>             |

## Defining a custom case header

For the above screenshot, the configuration in the environment looks like this:

#### **`environment.ts`**
  ```typescript
...

export const environment: ValtimoConfig = {
    ...
    customDossierHeader: {
        aansprakelijkstelling: [
            {
                labelTranslationKey: 'aansprakelijkstelling',
                columnSize: 12,
                textSize: 'xl',
                customClass: 'font-weight-bold'
            },
            {
                labelTranslationKey: 'aansprakelijkstelling.naam',
                propertyPaths: ['aanvrager.persoonsgegevens.voorletters', 'aanvrager.persoonsgegevens.achternaam'],
                columnSize: 6,
            },
            {
                propertyPaths: ['aanvrager.adres.woonplaats'],
                columnSize: 3,
                textSize: 'md',
                customClass: 'text-danger'
            },
            {
                columnSize: 3
            },
            {
                labelTranslationKey: 'aansprakelijkstelling.adres',
                propertyPaths: ['aanvrager.adres.adres', 'aanvrager.adres.huisnummer', 'aanvrager.adres.postcode', 'aanvrager.adres.woonplaats'],
                columnSize: 6,
                textSize: 'sm',
            },
            {
                labelTranslationKey: 'aansprakelijkstelling.telefoonnummer',
                propertyPaths: ['aanvrager.persoonsgegevens.telefoonnummer'],
                columnSize: 3,
                textSize: 'sm',
                noValueText: 'Nog niet bekend'
            },
        ]
    }
    ...
};
  ```

`customDossierHeader` is the main object that holds all custom case header configurations. Inside of this object, for
each case for which a custom case header is to be defined, an array can be added under a key with the case id. In the
example above, a custom case header configuration for a case with the id `aansprakelijkstelling` is added.

Each `customDossierHeaderItem` in `customDossierHeader` can have the following properties:

- `labelTranslationKey`*: a key for the label translation, this refers to a translation key in the translation files. 
This can also be used if you just want to show a text in the header without data from the document.
- `propertyPaths`*: an array of paths to the data from the document that you want to display, so this can also be 
multiple items that are placed one after the other.
- `columnSize`*: the column size based on Bootstrap columns (col-1, col-2, col-3, ..., col-12). Bootstrap divides a row
in 12 columns, if you keep adding blocks after you have filled the first 12 columns, the blocks will be pushed to the
next row. In this way you can keep adding blocks on multiple rows. If no `columnSize` is specified, the default size is 3.
- `textSize`: the size of the text for this item (xs, sm, md, lg, xl). If no textSize is specified, the default size is
md.
- `noValueText`: the text that will be shown if the data is not yet available in the document. If no `noValueText` is
specified, the default value is '-'.
- `customClass`: a string of classes to be applied to this item, with this a lot of freedom is provided in formatting
the custom header items. All Bootstrap classes are available by default, for further customisation classes need to be
added in your implementation's style sheets.

(* = this property can be added as the only property of a customDossierHeaderItem)