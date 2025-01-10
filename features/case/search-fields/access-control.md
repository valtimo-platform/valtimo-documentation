# Access control

Access to the search fields can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="329">Resource type</th><th width="143">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.document.domain.impl.searchfield.SearchField</code></td><td><code>view_list</code></td><td>Allows viewing search fields</td></tr></tbody></table>

### Examples

#### Permission to view all search fields

<pre class="language-json"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.document.domain.impl.searchfield.SearchField",
</strong>    "action": "view_list",
    "conditions": []
}
</code></pre>

#### Permission to view all search fields of one specific case type

```json
{
   "resourceType":"com.ritense.document.domain.impl.searchfield.SearchField",
   "action":"view_list",
   "conditions":[
      {
         "type":"field",
         "field":"id.document_definition_name",
         "operator":"==",
         "value":"evenementenvergunning"
      }
   ]
}
```

#### Permission to view one specific search field

```json
{
   "resourceType":"com.ritense.document.domain.impl.searchfield.SearchField",
   "action":"view_list",
   "conditions":[
      {
         "type":"field",
         "field":"key",
         "operator":"==",
         "value":"first-name"
      }
   ]
}
```

