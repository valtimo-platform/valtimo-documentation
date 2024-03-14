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
start making a custom theme. For the custom Carbon theme to work, it has to be loaded after the carbon.scss file, otherwise
all changes will be overwritten.

### Custom color palette

If you want to use custom colors, you can do so. It is recommended that the contrast between your custom color and 
`#FFFFFF` is 4.5:1 or higher. This can be checked by using the [WCAG Contrast Checker](https://contrastchecker.com) and 
setting your custom color as the background color and setting `#FFFFFF` as the foreground color.

If your custom color has a contrast ratio higher than 4.5:1, you can use the [Color Shades Generator](https://mdigi.tools/color-shades/)
to create 10 shades based on your color. These 10 colors will be your new values with `$custom-color-10` being the
lightest color and `$custom-color-100` being the darkest. 

_**Sidenote:**_ Please make sure that you never use red as the main color. Red means "danger" and it can have a negative
effect on the hierarchy of colors in the UI when used as the main color.

#### **`custom-carbon-theme.scss`**
```scss
/* These are the custom values based on hues */
$custom-color-100: #002547;
$custom-color-90: #002c54;
$custom-color-80: #003361;
$custom-color-70: #286198;
$custom-color-60: #2b79bd;
$custom-color-50: #61aedf;
$custom-color-40: #8acff2;
$custom-color-30: #aadcf6;
$custom-color-20: #c9e9f9;
$custom-color-10: #e9f6fd;

/* next, the default carbon themes are imported */
@use '@carbon/styles/scss/themes';
@use '@carbon/colors';

/* here we assign the themes we want to use as light themes */
$lightThemeVariables: (
        'g10': themes.$g10,
);

/* and here we assign the themes we want to use as dark themes */
$darkThemeVariables: (
        'g90': themes.$g90,
        'g100': themes.$g100,
);

/* this is where we override the default properties that are used in the light themes */
$lightThemeOverwriteVariables: (
        // Color 80
        active-primary: $custom-color-80,
        active-tertiary: $custom-color-80,
        // Color 70
        link-02: $custom-color-70,
        support-04: $custom-color-70,
        hover-primary-text: $custom-color-70,
        link-secondary: $custom-color-70,
        support-info: $custom-color-70,
        link-primary-hover: $custom-color-70,
        // Color 60
        interactive-01: $custom-color-60,
        interactive-03: $custom-color-60,
        interactive-04: $custom-color-60,
        link-01: $custom-color-60,
        focus: $custom-color-60,
        background-brand: $custom-color-60,
        interactive: $custom-color-60,
        border-interactive: $custom-color-60,
        link-primary: $custom-color-60,
        brand-01: $custom-color-60,
        brand-03: $custom-color-60,
        // Color 50
        inverse-support-04: $custom-color-50,
        support-info-inverse: $custom-color-50,
        // Color 40
        inverse-link: $custom-color-40,
        link-inverse: $custom-color-40,
        // Color 20
        highlight: $custom-color-20,
);

/* this is where we override the default properties that are used in the dark themes */
$darkThemeOverwriteVariables: (
        // Color 80
        active-primary: $custom-color-80,
        active-tertiary: $custom-color-80,
        highlight: $custom-color-80,
        // Color 70
        inverse-support-04: $custom-color-70,
        support-info-inverse: $custom-color-70,
        // Color 60
        interactive-01: $custom-color-60,
        background-brand: $custom-color-60,
        brand-01: $custom-color-60,
        brand-03: $custom-color-60,
        // Color 50
        support-04: $custom-color-50,
        support-info: $custom-color-50,
        interactive-04: $custom-color-50,
        interactive: $custom-color-50,
        border-interactive: $custom-color-50,
        // Color 40
        link-01: $custom-color-40,
        link-primary: $custom-color-40,
        // Color 30
        link-02: $custom-color-30,
        hover-primary-text: $custom-color-30,
        link-secondary: $custom-color-30,
        link-primary-hover: $custom-color-30,
);

@use '@carbon/styles/scss/theme' with (
  $theme: map-merge(themes.$g10, $lightThemeOverwriteVariables)
);

/* button colors are defined here */
@use '@carbon/styles/scss/components/button/tokens' as button-tokens with (
  $button-primary-active: $custom-color-80,
  $button-tertiary-active: $custom-color-80,
  $button-primary-hover: $custom-color-70,
  $button-tertiary-hover: $custom-color-70,
  $button-primary: $custom-color-60,
  $button-tertiary: $custom-color-60
);

/* here, all Carbon styles are included. This step is obligatory to use Carbon styling in your implementation */
@use '@carbon/styles';
@use '@carbon/grid';
@include grid.flex-grid();

/* Class names are generated for all available themes, so they can be used wherever necessary */
/* An example of a theme class: 'g10' */
@each $name, $variable in $lightThemeVariables {
  [data-carbon-theme='#{$name}'] {
    @include theme.theme($variable, $lightThemeOverwriteVariables);
  }
}

/* the same is done for the dark themes */
@each $name, $variable in $darkThemeVariables {
  [data-carbon-theme='#{$name}'] {
    @include theme.theme($variable, $darkThemeOverwriteVariables);
  }
}

/* now we activate the theme we just configured and apply it to the root */
:root {
  @include theme.theme(themes.$g10, $lightThemeOverwriteVariables);
  // if we use @include theme.theme(themes.$g90, $darkThemeOverwriteVariables); we will get the dark theme.
}

/* finally, we apply the correct custom background color to the background, side navigation and header bar */
body {
  background-color: var(--cds-background);
}

.cds--header{
  background-color: var(--cds-layer);
}

.cds--side-nav{
  background-color: var(--cds-layer);
}
```



