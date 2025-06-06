# Carbon design system

Carbon is IBM's open source design system, based on the IBM design language. As of major version 10, Valtimo uses Carbon for its user interface. It has been selected because of its clean and professional look, consistency, documentation and its large amount of components that fit Valtimo's purposes.

## Including Carbon in implementations

In order to make Carbon work with implementations, some small adjustments need to be made. Please refer to [the release notes of major version 10](../../../release-notes/major10/10.0.0/migration.md) for instructions on making these adjustments.

## Using Carbon

If Carbon is included in your implementation, you may also use its components to build functionality. On using Carbon correctly, refer to [its official documentation](https://carbondesignsystem.com/). When using its Angular components, referring to [the Angular storybook](https://angular.carbondesignsystem.com/?path=/docs/getting-started--docs) is recommended.

## Customizing Carbon theme

The theme used by Carbon can be customized to a large degree. By default, the libary `@valtimo/components` exports a theme from the following path: `"node_modules/@valtimo/components/assets/css/carbon.scss"`. Also, a stylesheet is exported to ensure compatibility with the previous Beagle theme, FormIO forms and other Carbon specific overrides that are necessary: `"node_modules/@valtimo/components/assets/css/compatibility.scss"`.

### Custom color palette

You can override the default Valtimo blue colors by adding these to your `styles.scss`. See the example below and replace the hex values with your custom values.

It is recommended that the contrast between your custom color and `#FFFFFF` is 4.5:1 or higher. This can be checked by using the [WCAG Contrast Checker](https://contrastchecker.com) and setting your custom color as the background color and setting `#FFFFFF` as the foreground color.

If your custom color has a contrast ratio higher than 4.5:1, you can use the [Color Shades Generator](https://mdigi.tools/color-shades/) to create 10 shades based on your color. These 10 colors will be your new values with `--vcds-color-10` being the lightest (almost white) color and `--vcds-color-100` being the darkest (almost black).

_**Sidenote:**_ Please make sure that you never use red as the main color. Red means "danger" and it can have a negative effect on the hierarchy of colors in the UI when used as the main color.

#### **`styles.scss`**

```scss
/* these are the colors that override the default Valtimo blue colors */
:root {
  --vcds-color-100: #100a0b;
  --vcds-color-90: #301d21;
  --vcds-color-80: #4f3038;
  --vcds-color-70: #6f434e;
  --vcds-color-60: #8f5664;
  --vcds-color-50: #a9707d;
  --vcds-color-40: #bc909a;
  --vcds-color-30: #cfb0b7;
  --vcds-color-20: #e2cfd4;
  --vcds-color-10: #f5eff1;
}
```
