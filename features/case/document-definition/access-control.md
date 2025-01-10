# Access control

Access to document definitions can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="357">Resource type</th><th width="111">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.document.domain.impl.JsonSchemaDocument</code></td><td><code>assign</code></td><td>Allows assigning users to a case document.</td></tr><tr><td></td><td><code>assignable</code></td><td>Allows users to be assigned to a case document.</td></tr><tr><td></td><td><code>create</code></td><td>Allows creating of a case document.</td></tr><tr><td></td><td><code>claim</code></td><td>Allows claiming of a case document.</td></tr><tr><td></td><td><code>delete</code></td><td>Allows deleting of a case document.</td></tr><tr><td></td><td><code>modify</code></td><td>Allows modifying of a case document.</td></tr><tr><td></td><td><code>view</code></td><td>Allows viewing of a case document.</td></tr><tr><td></td><td><code>view_list</code></td><td>Allows viewing of case documents.</td></tr><tr><td><code>com.ritense.document.domain.impl.JsonSchemaDocumentDefinition</code></td><td><code>create</code></td><td>Allows creating of a case document definition.</td></tr><tr><td></td><td><code>delete</code></td><td>Allows deleting of a case document definition.</td></tr><tr><td></td><td><code>modify</code></td><td>Allows modifying of a case document definition.</td></tr><tr><td></td><td><code>view</code></td><td>Allows viewing of a case document definition.</td></tr><tr><td></td><td><code>view_list</code></td><td>Allows viewing of case document definitions.</td></tr></tbody></table>

### Examples

#### Permission to view access to all case document definitions

<pre class="language-json"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.document.domain.impl.JsonSchemaDocumentDefinition",
</strong>    "action": "view",
    "conditions": []
}
</code></pre>

#### Permission to view access to all documents of one case document definition

```json
{
   "resourceType":"com.ritense.document.domain.impl.JsonSchemaDocument",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"documentDefinitionId.name",
         "operator":"==",
         "value":"evenementenvergunning"
      }
   ]
}
```

#### Permission to view access to one specific document definition

```json
{
   "resourceType":"com.ritense.document.domain.impl.JsonSchemaDocumentDefinition",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"id.name",
         "operator":"==",
         "value":"evenementenvergunning"
      }
   ]
}
```
