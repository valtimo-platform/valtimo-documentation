# Front-end plugins

## Introduction

For each plugin you configure in the back-end, your front-end implementation needs to know what components to use in 
order to configure your plugin, and to configure your plugin's actions.

## Adding a plugin to your implementation

The library `@valtimo/plugin` exports several pre-made plugins. In order to use these in your implementation, you need 
to import the plugin's module and the plugin's specification into your app module like so. Also, you need to import
`PLUGINS_TOKEN` to inject the specification.

For example:

#### **`app.module.ts`**
```typescript
...

import {
    PLUGINS_TOKEN,
    SmartDocumentsPluginModule,
    smartDocumentsPluginSpecification
} from '@valtimo/plugin';

...
```

Next, add the plugin module to the `imports` array of your app module, and add the specification to the array provided
by `PLUGINS_TOKEN` under the `providers` array in your app module.

For example:

#### **`app.module.ts`**
```typescript
...

@NgModule({
    ...
    imports: [
        ...
        SmartDocumentsPluginModule
    ],
    providers: [
        ...
        {
            provide: PLUGINS_TOKEN,
            useValue: [
                ...
                smartDocumentsPluginSpecification
            ],
        },
    ],
    ...
})
export class AppModule {
}
```
Your implementation should now be able to display the plugin, configure it, configure its actions, and be able to link
its actions to process activities.


## Developing your own front-end plugin

To develop your own front-end plugin, the library `@valtimo/plugin` provides several interfaces which your own front-end
plugin must conform to, in order to be used in your implementation.

### Your plugin-in specification

First you need to make a plugin specification, conforming to the interface `PluginSpecification`. Below is an example
specification with explanations for each property:

#### **`sample.plugin.specification.ts`**
```typescript
import {PluginSpecification} from '@valtimo/plguin';
import {SamplePluginConfigurationComponent} from './components/sample-plugin-configuration/sample-plugin-configuration.component';
import {SAMPLE_PLUGIN_LOGO_BASE64} from './assets';
import {SampleActionConfigurationComponent} from './components/sample-action-configuration/sample-action-configuration.component';

const samplePluginSpecification: PluginSpecification = {
    /* 
    The plugin definition key of your plugin. 
    This needs to be the same as the id received from the back-end
     */
    pluginId: 'sampleplugin',
    /* 
    A component of the interface PluginConfigurationComponent, used to configure the plugin itself.
     */
    pluginConfigurationComponent: SamplePluginConfigurationComponent,
    // Points to a Base64 encoded string, which contains the logo of your plugin. 
    pluginLogoBase64: SAMPLE_PLUGIN_LOGO_BASE64,
    functionConfigurationComponents: {
        /*
         For each plugin action id received from the back-end, a component is provided of the interface FunctionConfigurationComponent. 
         These are used to configure each plugin action.
         */
        'sample-action': SampleActionConfigurationComponent,
    },
    /* 
    For each language key your implementation supports, translation keys with a translation can be provided below. 
    These can then be used in your configuration component using the pluginTranslate pipe.
    At a minumum, the keys 'title' and 'description' need to be defined.
     */
    pluginTranslations: {
        nl: {
            title: 'Voorbeeld-plug-in',
            description: 'Een uitstekende plug-in om mee te beginnen.',
            ...
        },
        en: {
            title: 'Sample plugin',
            description: 'A great plugin to get started with.',
            ...
        },
        de: {
            title: 'Beispiel-Plugin',
            description: 'Ein tolles Plugin für den Einstieg.',
            ...
        },
    },
};

export {samplePluginSpecification};
```

### Your plugin logo

Plugin logos are provided as a Base64 encoded string. This string is then imported in your plugin specification as shown
above. Please be advised to keep the size down to a minimum, so resize your logo image before encoding it to Base64. 
A maximum height of 60 pixels is advised.

[This website](https://www.base64-image.de/) is good for encoding images to Base64. After uploading, click `show code`,
and then copy the string under `For use in <img> elements:`.

Here is a sample file of a Base64 encoded logo:

#### **`sample-plugin-logo.ts`**
```typescript
const SAMPLE_PLUGIN_LOGO_BASE64 =
    'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAgAAAAIACAYAAAD0eNT6AAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAABBJJREFUeNrswTEBAAAAwqD1T20Hb6AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAOA3AQYAAvAAAXL/+O0AAAAASUVORK5CYII=';

export {SAMPLE_PLUGIN_LOGO_BASE64};
```






