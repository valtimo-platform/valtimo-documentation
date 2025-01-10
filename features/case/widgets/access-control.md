# Access control

Access to the case widgets can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="329">Resource type</th><th width="143">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.case_.domain.tab.CaseWidgetTabWidget</code></td><td><code>view</code></td><td>Allows viewing a case widget</td></tr></tbody></table>

### Examples

#### Permission to view all case widget

<pre class="language-json"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.case_.domain.tab.CaseWidgetTabWidget",
</strong>    "action": "view",
    "conditions": []
}
</code></pre>

#### Permission to view all case widgets of one specific case type

```json
{
   "resourceType":"com.ritense.case_.domain.tab.CaseWidgetTabWidget",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"id.caseWidgetTab.id.caseDefinitionName",
         "operator":"==",
         "value":"evenementenvergunning"
      }
   ]
}
```

#### Permission to view one specific case widget

```json
{
   "resourceType":"com.ritense.case_.domain.tab.CaseWidgetTabWidget",
   "action":"view",
   "conditions":[
      {
         "type":"field",
         "field":"key",
         "operator":"==",
         "value":"personal-data"
      }
   ]
}
```

