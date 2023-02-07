# What is a data provider

A data provider is a simple way of exposing any kind of data through a single API endpoint. An engineer can expose the
data by writing a data provider. A data provider is useful in a scenario where the data retrieved from an API, should be
fully customisable while the API endpoint stays the same.

The data provider setup was created for a specific use-case: the admin of the application should be able to configure a
data source that should populate a dropdown list. The admin can pick any data provider from the user interface, without
any code changes.

# How does a data provider work

The API that exposes the data, has the following format:

```
GET /api/v1/data/my-catagory?param1=value1&param2=value2
```

In the above example, the path-variable `my-category` and the query-parameters `param1=value1`
and `param2=value2` are all passed to all data providers. The data provider can then decide whether to return data or
not. If multiple data providers return data, an error is thrown.

# How to create a data provider

A data provider can be created by extending the property `DataProvider<MyDataType>`. Where the `MyDataType` is a type of
data that is returned through the API. The data provider must be a Spring bean.

The code below shows an example of a data provider that provide statuses for a shipment:

```java

@Component
public class StatusListDataProvider extends Provider<List<String>> {

    @Override
    public Boolean supportsCategory(String category) {
        return category.equals("shipment-status-list");
    }

    @Override
    public List<Status> get(Map<String, Any> query) {
        if ("in-contract".equals(query.get("milestone"))) {
            return List.of("contract-send", "contract-signed");
        } else if ("in-invoice".equals(query.get("milestone"))) {
            return List.of("invoice-send", "invoice-payed");
        } else {
            return null;
        }
    }

}
```

The data provider in the example above can then be called with the following API:

```
GET /api/v1/data/shipment-status-list?milestone=in-contract

Response status: 200 OK
Response body:   ["contract-send", "contract-signed"]
```

The function `supportsCategory(...)` decides whether the data provider should return data based on a category. In the
example above, the data provider will only be called when the category is`"shipment-status-list"`.

The function `get(...)` is responsible for returning the data. When the function returns `null`, another data provider
could be called to provide data for the same category.
