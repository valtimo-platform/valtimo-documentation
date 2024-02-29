# ZonedLocalDateTimeDeserializer
This deserializer supports the deserialization of ISO-8601 values with a zone offset or 'Z' to LocalDateTime
The zone difference between the value and local time is taken into account during the conversion.
A value without zone information will be deserialized into a LocalDateTime directly.

## Usage
There are several ways to apply a deserializer to the code. Some are listed below.

###  Application wide

```kotlin
@Bean
fun documentInformatieObjectMixinCustomizer(): Jackson2ObjectMapperBuilderCustomizer {
    return Jackson2ObjectMapperBuilderCustomizer { builder: Jackson2ObjectMapperBuilder ->
        builder.deserializerByType(LocalDateTime::class.java, ZonedLocalDateTimeDeserializer())
    }
}
```

### Directly on the property

If there's full control over the value class, the deserializer can be configured directly using the `JsonDeserialize` annotation:

```kotlin
class DocumentInformatieObject(
    @get:JsonDeserialize(using = ZonedLocalDateTimeDeserializer::class)
    val beginRegistratie: LocalDateTime
)
```

### Via a mixin
Considering the following mixin:
```kotlin
abstract class DocumentInformatieObjectMixin(
    @get:JsonDeserialize(using = ZonedLocalDateTimeDeserializer::class)
    val beginRegistratie: LocalDateTime
)
```

It can configured via a customizer:
``` kotlin
@Bean
fun documentInformatieObjectMixinCustomizer(): Jackson2ObjectMapperBuilderCustomizer {
    return Jackson2ObjectMapperBuilderCustomizer { builder: Jackson2ObjectMapperBuilder ->
        builder.mixIn(DocumentInformatieObject::class.java, DocumentInformatieObjectMixin::class.java)
    }
}

abstract class DocumentInformatieObjectMixin(
    @get:JsonDeserialize(using = ZonedLocalDateTimeDeserializer::class)
    val beginRegistratie: LocalDateTime
)
```

or a module:

```kotlin
@Bean
fun documentInformatieObjectMixinModule() : SimpleModule {
    return SimpleModule("documentInformatieObjectMixinModule")
        .setMixInAnnotation(DocumentInformatieObject::class.java, DocumentInformatieObjectMixin::class.java)
}
```

