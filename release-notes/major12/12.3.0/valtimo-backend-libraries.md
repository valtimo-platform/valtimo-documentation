# Backend libraries 12.3.0

## New Features

The following features were added:

* **Added support for updating the submission data inside a Form Flow SpEL expressions**

  A Form flow SpEL expressions now accepts updating the submission data.
  See [this page](/using-valtimo/form-flow/create-form-flow-definition.md#expressions) for more information.

## Bugfixes

The following bugs were fixed:

* **Form flow data is now correct when navigating back and forward**

  The data that a user entered in the form of a form flow is now correctly saved and displayed again when
  navigating back and forward in a form flow.

  If the user makes changes in a previous step, any later step will now either show correct data, or not show any data
  at all.

* **Form flow spamming Submit button**

  A double click on the Submit button in a form flow will now properly go to the next step and not to any step further
  than that.

* **Form IO Data Grid and Edit Grid are now prefilled correctly**

  When a form is opened the show a Data Grid or Edit Grid, the form will now only fill the fields that should be
  prefilled.


## Breaking changes

The following breaking changes were introduced:

* **Breaking change1**

* **Breaking change2**

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Deprecations

The following was deprecated:

* **WebClient is no longer the default HTTP client**
    
    We have transitioned from using the WebClient class to RestClient. For more details, see the [overview](https://docs.spring.io/spring-framework/reference/integration/rest-clients.html).
    
    The primary reason for this switch is to adopt a simpler client that does not rely on reactive programming concepts. Most calls in Valtimo require synchronous execution, making WebClient less suitable.
    
    Constructors in affected classes now use RestClient.Builder instead of WebClient.Builder.
    
    The default HTTP client is now Apache Client v5.x.
    For more details, see [ApacheRequestFactoryCustomizer](https://github.com/valtimo-platform/valtimo-backend-libraries/blob/b0941b2ca161601094203b38ac639f1a809988a8/contract/src/main/kotlin/com/ritense/valtimo/contract/client/ApacheRequestFactoryCustomizer.kt).
    
    A new configuration class has been introduced to modify two main timeout settings.
    For more information, see [ValtimoHttpRestClientConfigurationProperties](https://github.com/valtimo-platform/valtimo-backend-libraries/blob/b0941b2ca161601094203b38ac639f1a809988a8/contract/src/main/kotlin/com/ritense/valtimo/contract/client/ValtimoHttpRestClientConfigurationProperties.kt).
    
    Logging with the new Apache client can be configured as follows:
    ```yaml
      logging:
          level:
              org.apache.http: DEBUG
    ```

* **Methods inside ClientTools**

  Use of WebClient is deprecated, this was used before:
  - fun <T> getTypedPage(responseClass: Class<out T>): ParameterizedTypeReference<Page<T>> {
  - fun zgwErrorHandler(): ExchangeFilterFunction {

Instructions on how to migrate to this version of Valtimo can be found [here](migration.md).

## Known issues

This version has the following known issues:

* **Form flow - form data can disappear when making a change in a previous step**

  When a user goes back to the form of a previous step. Makes changes. Then goes to the next step again, the form might
  miss some of the data that the user did enter before going back. This has been done intentionally and only happens
  when new data submitted in a previous steps can affect existing data in later steps.

* **Issue2**
  * Discovered in version x.x.x
  * Describe what can be done to work around the issue
