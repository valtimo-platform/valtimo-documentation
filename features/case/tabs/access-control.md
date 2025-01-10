# Access control

Access to the case tabs can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="357">Resource type</th><th width="111">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.case.domain.CaseTab</code></td><td><code>view</code></td><td>Allows viewing tabs of a case.</td></tr></tbody></table>

### Examples

#### Permission to view all tabs

<pre class="language-json"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.case.domain.CaseTab",
</strong>    "action": "view",
    "conditions": []
}
</code></pre>

#### Permission to view all tabs of one specific case type

```json
{
   "resourceType":"com.ritense.case.domain.CaseTab",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"id.caseDefinitionName",
         "operator":"==",
         "value":"evenementenvergunning"
      }
   ]
}
```

#### Permission to view one specific tab

```json
{
   "resourceType":"com.ritense.case.domain.CaseTab",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"id.key",
         "operator":"==",
         "value":"summary"
      }
   ]
}
```
