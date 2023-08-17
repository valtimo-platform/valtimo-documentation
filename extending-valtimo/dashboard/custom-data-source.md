# Creating custom data sources

## Back-end

The dependency `com.ritense.valtimo:dashboard` can be used to develop a back-end for a data source.

### Data source specification

First, a data source specification using the `@WidgetDataSource` annotation needs to be created. Below is an example
data source:

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

The function can have either 0 or 1 argument. The single argument must be an object that contains the same fields that
are defined in the front end and configured by the admin. For example:

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
