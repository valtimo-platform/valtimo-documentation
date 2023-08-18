# Creating custom data sources

## Back-end

The dependency `com.ritense.valtimo:dashboard` is required to develop a data source in the Valtimo back-end.

### Data source specification

Data source specifications can be created using the `@WidgetDataSource` on a method in a Spring bean. Below is an
example data source:

```kotlin
@Component
class RandomNumberWidgetDataSource {

    @WidgetDataSource(key = "randomNumber", title = "Random number")
    fun randomNumberDataSource(properties: RandomNumberDataSourceProperties): RandomNumberResult {
        return RandomNumberResult(Random.nextInt(properties.from, properties.to))
    }
}
```

The `@Component` is necessary to register the new data source as a Spring bean.

The data source key `randomNumber` must be unique and is used the identify the data source. The same key must also be
used in the front end data source.

The function can be named anything.

If the datasource requires any configuration this will be passed in through the arguments of the function. All
properties should be contained in a single object that is used as the argument for this function. The configuration from
the front-end will be deserialized to this type, so the json structure should match that of the object. If no
configuration is required the argument can be left out.
Below is an example of a properties object that can be passed to the data source function.

```kotlin
data class RandomNumberDataSourceProperties(
    val from: Long = 0,
    val to: Long = 10
)
```

The function return value can be an object that contains anything. But ideally uses one of the following interfaces:

- `HasLabel`
- `HasNumberValue`
- `HasNumberValues`
- `HasTotal`

For example:

```kotlin
data class RandomNumberResult(
    override val value: Long
) : HasNumberValue
```
