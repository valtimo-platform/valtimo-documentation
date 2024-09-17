
# Rest Client Configuration

The default HTTP client is now Apache Client v5.x.
The `HttpComponentsClientHttpRequestFactory` has 2 main timeouts that can be configured:
These can be set using the following properties:
```yaml
valtimo:
    http:
        rest-client:
          connectTimeout: 5 # Default 5 seconds
          connectionRequestTimeout: 5 # Default 5 seconds
```
[Spring documentation](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/http/client/HttpComponentsClientHttpRequestFactory.html)
