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

### Your plugin specification

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
    These can then be used in your configuration component using the pluginTranslate pipe or the PluginTranslationService.
    At a minumum, the keys 'title' and 'description' need to be defined.
    Also, don't forget to add a translation key for each function key. In this case, we add a key 'sample-action'.
     */
    pluginTranslations: {
        nl: {
            title: 'Voorbeeld-plug-in',
            description: 'Een uitstekende plug-in om mee te beginnen.',
            'sample-action': 'Voorbeeldactie',
            configurationTitle: 'Configuratienaam',
            url: 'URL',
            message: 'Bericht',
            ...
        },
        en: {
            title: 'Sample plugin',
            description: 'A great plugin to get started with.',
            'sample-action': 'Sample action',
            configurationTitle: 'Configuration name',
            url: 'URL',
            message: 'Message',
            ...
        },
        de: {
            title: 'Beispiel-Plugin',
            description: 'Ein tolles Plugin für den Einstieg.',
            'sample-action': 'Beispielaktion',
            configurationTitle: 'Konfigurationsname',
            url: 'URL',
            message: 'Nachricht',
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

### Your plugin configuration component

As shown in the [plugin specification section](#your-plugin-specification), your plugin configuration component needs to
conform to the interface `PluginConfigurationComponent`. Below the interface is shown, with a comment for each required
property.

#### **`plugin.ts`**
```typescript
...

/* 
The required data outputted from the component.
In each case, a configuration title must be provided by your configuration component.
The rest of the properties must conform to the properties expected by the back-end.
*/
interface PluginConfigurationData {
    configurationTitle: string;
    [key: string]: any;
}

...

/*
The generic interface for a configuration component.
All of these properties must be implemented by your plugin configuration component,
since this interface is extended below.
*/
interface ConfigurationComponent {
    /*
    An observable your component must subscribe to.
    If this observable is triggered, your component must check if its configuration data is valid,
    and if so, emit this data on the configuration EventEmitter from the interface below.
     */
    save$: Observable<void>;
    /* 
    A boolean observable which your component must subscribe to. 
    If true, all input in your component must be disabled.
     */
    disabled$: Observable<boolean>;
    // The plugin definition key provided to your component. For our sample plugin, this would be 'sampleplugin'
    pluginId: string;
    /*
    When the values of the inputs in your configuration component change,
    your configuration component must continuously check whether the configuration data (all inputs combined) is valid.
    This EventEmitter outputs a boolean. So if the data is valid, output 'true', if invalid, output 'false'.
     */
    valid: EventEmitter<boolean>;
}

interface PluginConfigurationComponent extends ConfigurationComponent {
    /* 
    An observable input which includes configuration data if the plugin had already been saved previously,
    and is now being modified. Subscribe to this observable to prefill the input fields in your component.
     */
    prefillConfiguration$?: Observable<PluginConfigurationData>;
    /*
    As mentioned before, if the observable of the 'save$' input property is triggered, 
    check if your configuration data is valid. If so, output this data through this EventEmitter. 
     */
    configuration: EventEmitter<PluginConfigurationData>;
}

...
```

#### Typing your plugin configuration data

As mentioned, your plugin configuration component listens to prefill data of the interface `PluginConfigurationData`, 
and outputs configuration data of this same interface. It is advised to extend this interface and further specify what 
data your plugin requires. For our sample plugin, this would be:

#### **`sample-plugin-config.ts`**
```typescript
import {PluginConfigurationData} from '@valtimo/plugin';

interface SamplePluginConfig extends PluginConfigurationData {
    url: string;
}

export {SamplePluginConfig};
```

#### Implementing your plugin configuration component

Taking all the information above into account, we can now start implementing our plugin configuraiton component for our
sample plugin. You are free to implement this in any way you want, as long as you conform to the interfaces. Below is
sample code on implementing the component using components from the library `@valtimo/user-interface`.

#### **`sample-plugin-configuration.component.ts`**
```typescript
import {Component, EventEmitter, Input, OnDestroy, OnInit, Output} from '@angular/core';
import {PluginConfigurationComponent} from '@valtimo/plugin';
import {BehaviorSubject, combineLatest, Observable, Subscription, take, tap} from 'rxjs';
import {SamplePluginConfig} from '../models';

@Component({
    selector: 'valtimo-sample-plugin-configuration',
    templateUrl: './sample-plugin-configuration.component.html',
    styleUrls: ['./sample-plugin-configuration.component.scss'],
})
export class SamplePluginConfigurationComponent
    // Our components explicitly implements the PluginConfigurationComponent interface
    implements PluginConfigurationComponent, OnInit, OnDestroy
{
    @Input() save$: Observable<void>;
    @Input() disabled$: Observable<boolean>;
    @Input() pluginId: string;
    // If our plugin had already been saved, we expect a prefill configuration of the type SamplePluginConfig
    @Input() prefillConfiguration$: Observable<SamplePluginConfig>;

    // If our configuration data changes, we must output whether it is valid or not
    @Output() valid: EventEmitter<boolean> = new EventEmitter<boolean>();
    // If our configuration is valid, we output a configuration of the type SamplePluginConfig
    @Output() configuration: EventEmitter<SamplePluginConfig> =
        new EventEmitter<SamplePluginConfig>();

    private saveSubscription!: Subscription;

    private readonly formValue$ = new BehaviorSubject<SamplePluginConfig | null>(null);
    private readonly valid$ = new BehaviorSubject<boolean>(false);

    ngOnInit(): void {
        this.openSaveSubscription();
    }

    ngOnDestroy() {
        this.saveSubscription?.unsubscribe();
    }

    formValueChange(formValue: SamplePluginConfig): void {
        this.formValue$.next(formValue);
        this.handleValid(formValue);
    }

    private handleValid(formValue: SamplePluginConfig): void {
        // Our configuration is valid when a configuration title and url are defined
        const valid = !!(formValue.configurationTitle && formValue.url);

        this.valid$.next(valid);
        this.valid.emit(valid);
    }

    private openSaveSubscription(): void {
        /* 
        If the save observable is triggered, we check if our configuration is valid, and if so,
        we output the configuration using the configuration EventEmitter.
         */
        this.saveSubscription = this.save$?.subscribe(save => {
            combineLatest([this.formValue$, this.valid$])
                .pipe(take(1))
                .subscribe(([formValue, valid]) => {
                    if (valid) {
                        this.configuration.emit(formValue);
                    }
                });
        });
    }
}
```

The corresponding template file would look like this:

#### **`sample-plugin-configuration.component.html`**
```angular2html
<v-form
    (valueChange)="formValueChange($event)"
    *ngIf="{
        disabled: disabled$ | async,
        prefill: prefillConfiguration$ ? (prefillConfiguration$ | async) : null
    } as obs"
>
    <v-input
        name="configurationTitle"
        [title]="'configurationTitle' | pluginTranslate: pluginId | async"
        [margin]="true"
        [defaultValue]="obs.prefill?.configurationTitle"
        [disabled]="obs.disabled"
        [required]="true"
    >
    <v-input
        name="url"
        [title]="'url' | pluginTranslate: pluginId | async"
        [margin]="true"
        [defaultValue]="obs.prefill?.url"
        [disabled]="obs.disabled"
        [required]="true"
    >
    </v-input>
</v-form>
```

### Function configuration components

Each plugin action received from the back-end must have a corresponding function configuration component in your
front-end. Implementing these components works in much the same way as implementing the plugin configuration component,
so I will not go into as much detail as before. The only difference is that function configuration component
does not have to provide a configuration title. Below is sample code for our sample plugin action with the id 
`'sample-action'`:

#### **`sample-action-config.ts`**
```typescript
interface SampleActionConfig {
    message: string;
}

export {SampleActionConfig};
```

#### **`sample-action-configuration.component.ts`**
```typescript
import {Component, EventEmitter, Input, OnDestroy, OnInit, Output} from '@angular/core';
import {FunctionConfigurationComponent} from '@valtimo/plugin';
import {BehaviorSubject, combineLatest, Observable, Subscription, take, tap} from 'rxjs';
import {SampleActionConfig} from '../models';

@Component({
    selector: 'valtimo-sample-action-configuration',
    templateUrl: './sample-action-configuration.component.html',
    styleUrls: ['./sample-action-configuration.component.scss'],
})
export class SamplePluginConfigurationComponent
    // Our components explicitly implements the FunctionConfigurationComponent interface
    implements FunctionConfigurationComponent, OnInit, OnDestroy
{
    @Input() save$: Observable<void>;
    @Input() disabled$: Observable<boolean>;
    @Input() pluginId: string;
    @Input() prefillConfiguration$: Observable<SampleActionConfig>;
    @Output() valid: EventEmitter<boolean> = new EventEmitter<boolean>();
    @Output() configuration: EventEmitter<SampleActionConfig> =
        new EventEmitter<SampleActionConfig>();

    private saveSubscription!: Subscription;

    private readonly formValue$ = new BehaviorSubject<SampleActionConfig | null>(null);
    private readonly valid$ = new BehaviorSubject<boolean>(false);

    ngOnInit(): void {
        this.openSaveSubscription();
    }

    ngOnDestroy() {
        this.saveSubscription?.unsubscribe();
    }

    formValueChange(formValue: SampleActionConfig): void {
        this.formValue$.next(formValue);
        this.handleValid(formValue);
    }

    private handleValid(formValue: SampleActionConfig): void {
        const valid = !!(formValue.message);

        this.valid$.next(valid);
        this.valid.emit(valid);
    }

    private openSaveSubscription(): void {
        this.saveSubscription = this.save$?.subscribe(save => {
            combineLatest([this.formValue$, this.valid$])
                .pipe(take(1))
                .subscribe(([formValue, valid]) => {
                    if (valid) {
                        this.configuration.emit(formValue);
                    }
                });
        });
    }
}
```

#### **`sample-action-configuration.component.html`**
```angular2html
<v-form
    (valueChange)="formValueChange($event)"
    *ngIf="{
        disabled: disabled$ | async,
        prefill: prefillConfiguration$ ? (prefillConfiguration$ | async) : null
    } as obs"
>
    <v-input
        name="message"
        [title]="'message' | pluginTranslate: pluginId | async"
        [margin]="true"
        [defaultValue]="obs.prefill?.message"
        [disabled]="obs.disabled"
        [required]="true"
    >
</v-form>
```

### Plugin translations

#### Plugin translate pipe

As you might have noticed, the template code show above uses the `pluginTranslate` pipe to show translations from the 
plugin specification. To use this, first import import `PluginTranslatePipeModule` from `@valtimo/plugin` and add it
to the `imports` array of your plugin module. Now you can use the `pluginTranslate` pipe in your templates. It uses the
following syntax:

#### **`sample-translation-pipe.component.html`**
```angular2html
<span>
    {{ 'translationKey' | pluginTranslate: pluginId | async" }}
</span>
```

The pipe returns an observable, so do not forget to add an `| async` at the end.

`translationKey` refers to one of the translation keys specified in your plugin specification.

`pluginId` refers to your plugin's definition key. For our sample plugin, this would be `sampleplugin`.
It is provided by the `pluginId` input on your configuration component.

#### Plugin translation service

If you wish to translate inside your component code (as opposed to inside the template using the pipe),
you may use the `PluginTranslationService` exported by `@valtimo/plugin`. It supports a `translate` method, which 
returns an observable containing your translation, and an `instant` method, which returns a string containing your
translation.

### Plugin module

Finally, after implementing our components and specification, we should not forget to define a module for our plugin.
This module, together with the specification, is then imported in our app module as shown in [this section](#adding-a-plugin-to-your-implementation).

Our sample plugin module would look like this:
#### **`sample-plugin.module.ts`**
```typescript
import {NgModule} from '@angular/core';
import {CommonModule} from '@angular/common';
import {PluginTranslatePipeModule} from '../../pipes';
import {FormModule, InputModule} from '@valtimo/user-interface';
import {SamplePluginConfigurationComponent} from './components/sample-plugin-configuration/sample-plugin-configuration.component';
import {SampleActionConfigurationComponent} from './components/sample-action-configuration/sample-action-configuration.component';

@NgModule({
    declarations: [SamplePluginConfigurationComponent, SampleActionConfigurationComponent],
    imports: [CommonModule, PluginTranslatePipeModule, FormModule, InputModule],
    exports: [SamplePluginConfigurationComponent, SampleActionConfigurationComponent],
})
export class DocumentenApiPluginModule {}
```





