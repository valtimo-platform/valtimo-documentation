# Creating custom data sources

## Front-end

To develop a front-end for a data source, the library `@valtimo/dashboard` provides several interfaces which data source
front-ends must conform to, in order to be used in an implementation.

### Data source specification

First, a data source specification conforming to the `DataSourceSpecification` interface needs to be created. Below is an example
specification with explanations for each property:

#### **`sample-data-source.specification.ts`**
```typescript
import {PluginSpecification} from '@valtimo/plugin';
import {SamplePluginConfigurationComponent} from './components/sample-plugin-configuration/sample-plugin-configuration.component';
import {SAMPLE_PLUGIN_LOGO_BASE64} from './assets';
import {SampleActionConfigurationComponent} from './components/sample-action-configuration/sample-action-configuration.component';

const sampleDataSourceSpecification: DataSourceSpecification = {
    /* 
    The data source key. This needs to be the same as the id received from the back-end.
     */
    dataSourceKey: 'sample-data-source',
    /* 
    A component of the interface DataSourceConfigurationComponent, used to configure the data source.
     */
    configurationComponent: SampleConfigurationComponent,
    /* 
    For each language key an implementation supports, translation keys with a translation are provided below. 
    These can then be used in configuration components using the widgetTranslate pipe or the WidgetTranslationService.
    At a minumum, the key 'title' needs to be defined.
     */
    translations: {
        nl: {
            title: 'Databron',
            ...
        },
        en: {
            title: 'Data source',
            ...
        },
        de: {
            title: 'Datenquelle',
            ...
        },
    },
};

export {sampleDataSourceSpecification};
```