# Auto deployment plugin configurations

Plugin configurations can be auto deployed by creating one/multiple files under the 'resources' folder that will hold
an array of configurations.

The file name must end in '.pluginconfig.json' so that is picked up for auto deployment.

Here is an example of a configuration:

```json
[
  {
    "id": "683d80a5-01ed-440f-bdea-03ae501ae62b",
    "title": "My plugin configuration",
    "pluginDefinitionKey": "my-plugin",
    "properties": {
      "myProperty": "myProperty",
      "mySecret": "${MY_SECRET}"
    }
  },
  {
    "id": "3079d6fe-42e3-4f8f-a9db-52ce2507b7ee",
    "title": "My plugin two",
    "pluginDefinitionKey": "my-plugin-two",
    "properties": {
      "url": "http://localhost:8080/some/url/",
      "myPluginId": "683d80a5-01ed-440f-bdea-03ae501ae62b"
    }
  }
]
```

The 'id' property is optional and if absent the id will be auto generated, but it is useful if
some other plugin requires the id of the previous plugin in its properties as plugins are deployed by the order in which 
they are in the file.

Each property in 'properties' object can be resolved according to environment variables by using '${MY_ENV_VAR}' syntax.




