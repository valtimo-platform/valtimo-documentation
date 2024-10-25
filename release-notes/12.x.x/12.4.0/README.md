# 12.4.0

{% hint style="warning" %}
This release contains a potentially breaking change. More information can be found [here](./#webclient-has-been-replaced-by-restclient).
{% endhint %}

## New features

#### Task panel

The user tasks on a case detail page can now be shown in a task panel. Using a task panel, the user can fill in and complete the form while being able to see and navigate through the different case tabs. Administrators can configure whether tasks should be shown in the modal or in the task panel. More information about this feature can be found [here](https://github.com/valtimo-platform/valtimo-documentation/blob/next-minor/using-valtimo/tasks/task-panel.md).

{% hint style="info" %}
**Note**: to enable the task panel feature, the following feature toggle should be set in the Valtimo frontend configuration: `enableTaskPanel`
{% endhint %}

#### New process link type: URL

A new way of configuring forms is available: the URL. By configuring a URL process link on a start event or user task, users will be redirected to the configured URL. Using this feature, external forms can be used to start a process or submit a user task.

#### ZGW - filtered document types

When selecting a document type (informatieobjecttype), e.g. when uploading a document, the list of options is now filtered. Only documenttypes are available that:

* are final/published
* have a valid start date that is in the past
* do not have an end date that already passed

#### ZGW - documents list pagination

The document list now supports pagination, when the Documenten API supports retrieving paginated results.

#### System audit events

When audit events are initiated by the system, the author is now 'System' instead of 'Anonymous'. Authors of historic events are migrated.

## Bugfixes

#### Forms and Form Flows

* When navigating back and forth between Form Flow steps, sometimes the data was stored incorrectly.&#x20;
* When the user clicked the submit button in a Form Flow multiple times, the Form Flow would incorrectly skip one or more steps.
* Form.io datagrid and editgrid components are now prefilled correctly.
* Updated form process links where the form definition has been changed, were not processed correctly.

{% hint style="danger" %}
A known issue is that, when a user goes back and forth between Form Flow steps, certain data is lost. This is intended behaviour that only occurs when data in previous steps has been changed, potentially affecting data already submitted in later steps.
{% endhint %}

## Extending Valtimo/for developers

#### WebClient has been replaced by RestClient

* The primary reason for this switch is to adopt a simpler client that does not rely on reactive programming concepts. Most calls in Valtimo require synchronous execution, making WebClient less suitable.
* Constructors in affected classes now use `RestClient.Builder` instead of `WebClient.Builder`.
* The default HTTP client is now Apache Client v5.x. For more details on how to override/adjust this, see `com.ritense.valtimo.contract.client.ApacheRequestFactoryCustomizer` class. More information can also be found in the [Spring documentation](https://docs.spring.io/spring-boot/reference/io/rest-client.html#io.rest-client.restclient.customization).
* Two main timeout settings are configurable through the application properties: `valtimo.http.rest-client.connectTimeout` and `valtimo.http.rest-client.connectionRequestTimeout`, both in seconds. More information on these properties can be found in the [Rest client configuration](https://github.com/valtimo-platform/valtimo-documentation/blob/next-minor/reference/rest-client-configuration.md).
* Logging with the new Apache client can be configured by setting the `logging.level.org.apache.http` application property to the desired log level.
* Additionally, a custom logger has been implemented to create extensive log reports on HTTP requests and responses. This logger can be enabled by setting the `logging.level.com.ritense.valtimo.web.logging.LoggingRestClientCustomizer` property to `DEBUG`.
* As part of this replacement, two methods in the `com.ritense.zgw.ClientTools` class have been deprecated:&#x20;
  * `getTypedPage(responseClass: Class<out T>): ParameterizedTypeReference<Page<T>>`
  * `zgwErrorHandler(): ExchangeFilterFunction`

#### Updating the Form Flow submission data

Using SpEL expressions, Form Flow submission data can now be changed. More information can be found [here](https://github.com/valtimo-platform/valtimo-documentation/blob/next-minor/using-valtimo/form-flow/create-form-flow-definition.md#expressions).\
