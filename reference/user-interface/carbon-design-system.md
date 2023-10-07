# Carbon design system

Carbon is IBM's open source design system, based on the IBM design language. As of major version 10, Valtimo uses Carbon
for its user interface. It has been selected because of its clean and professional look, consistency, documentation and
its large amount of components that fit Valtimo's purposes.

## Including Carbon in implementations

In order to make Carbon work with implementations, some small adjustments need to be made. Please refer to [the release
notes of major version 10](/release-notes/major10/10.0.0/migration.md) for instructions on making these adjustments.

## Using Carbon

If Carbon is included in your implementation, you may also use its components to build functionality. On using Carbon
correctly, refer to [its official documentation](https://carbondesignsystem.com/). When using its Angular components,
referring to [the Angular storybook](https://angular.carbondesignsystem.com/?path=/story/components-welcome--to-carbon-angular) is recommended.

## Customizing Carbon theme

The theme used by Carbon can be customized to a large degree. By default, the libary `@valtimo/components` exports a
theme from the following path: `"node_modules/@valtimo/components/assets/css/carbon.scss"`. Also, a stylesheet is 
exported to ensure compatibility with the previous Beagle theme:
`"node_modules/@valtimo/components/assets/css/carbon-beagle-compatibility.scss"`.

Instead of using `"node_modules/@valtimo/components/assets/css/carbon.scss"` in your implementation, you may also include
a custom theme. This needs to be in the form of a `.scss` stylesheet. Please refer to the following example on how to
start making a custom theme.

#### **`custom-carbon-theme.scss`**
```scss
/* first some SCSS color variables are defined */
$ritense-blue-80: #003361;
$ritense-blue-70: #224f76;
$ritense-blue-60: #456a8c;
$ritense-blue-50: #4589ff;
$ritense-blue-40: #8aa1b6;
$ritense-blue-30: #acbdcc;
$ritense-blue-20: #cfd8e1;
$ritense-blue-10: #f1f4f6;

/* next, the default carbon themes are imported */
@use '@carbon/styles/scss/themes';

/* a Carbon theme is selected, and SCSS functionality is used to override some variables used inside it */
@use '@carbon/styles/scss/theme' with (
  $theme:
    map-merge(
      /* In this case, the white theme is used and extended. Other options are: g10, g90 and g100 */
      themes.$white,
      (
        // Blue 80
        /* All properties using IBM blue are overridden with Ritense blue values */
        active-primary: $ritense-blue-80,
        active-tertiary: $ritense-blue-80,
        button-primary-active: $ritense-blue-80,
        button-tertiary-active: $ritense-blue-80,
        // Blue 70
        link-02: $ritense-blue-70,
        support-04: $ritense-blue-70,
        hover-primary-text: $ritense-blue-70,
        link-secondary: $ritense-blue-70,
        support-info: $ritense-blue-70,
        link-primary-hover: $ritense-blue-70,
        // Blue 60
        interactive-01: $ritense-blue-60,
        interactive-03: $ritense-blue-60,
        interactive-04: $ritense-blue-60,
        link-01: $ritense-blue-60,
        focus: $ritense-blue-60,
        background-brand: $ritense-blue-60,
        interactive: $ritense-blue-60,
        border-interactive: $ritense-blue-60,
        link-primary: $ritense-blue-60,
        button-primary: $ritense-blue-60,
        button-tertiary: $ritense-blue-60,
        brand-01: $ritense-blue-60,
        brand-03: $ritense-blue-60,
        // Blue 50
        inverse-support-04: $ritense-blue-50,
        support-info-inverse: $ritense-blue-50,
        // Blue 40
        inverse-link: $ritense-blue-40,
        link-inverse: $ritense-blue-40,
        // Blue 20
        highlight: $ritense-blue-20
      )
    )
);

/* Other Carbon themes are available for use*/
$themeVariables: (
  'g10': themes.$g10,
  'g90': themes.$g90,
  'g100': themes.$g100,
);

/* Class names are generated for all available themes, so they can be used wherever necessary */
/* An example of a theme class: 'carbon-theme-g10' */
@each $name, $variable in $themeVariables {
  .carbon-theme-#{$name} {
    @include theme.theme($variable);
  }
}


/* Finally, all Carbon styles are included. This step is obligatory to use Carbon styling in your implementation */
@use '@carbon/styles';
```



