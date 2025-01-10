# Access control

Access to dashboards can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="357">Resource type</th><th width="111">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.dashboard.domain.Dashboard</code></td><td><code>view</code></td><td>Allows viewing the data of one dashboard.</td></tr><tr><td></td><td><code>view_list</code></td><td>Allows viewing the dashboard tabs.</td></tr></tbody></table>

### Examples

#### Permission to view all dashboards and data

<pre class="language-json"><code class="lang-json">[
    {
<strong>        "resourceType": "com.ritense.dashboard.domain.Dashboard",
</strong>        "action": "view",
        "conditions": []
    },
    {
        "resourceType": "com.ritense.dashboard.domain.Dashboard",
        "action": "view_list",
        "conditions": []
    }
]
</code></pre>

#### Permission to view the data of one specific dashboard

```json
[
   {
      "resourceType": "com.ritense.dashboard.domain.Dashboard",
      "action":"view",
      "conditions":[
         {
            "type":"field",
            "field":"key",
            "operator":"==",
            "value":"management-dashboard"
         }
      ]
   },
   {
      "resourceType": "com.ritense.dashboard.domain.Dashboard",
      "action":"view_list",
      "conditions":[
         {
            "type":"field",
            "field":"key",
            "operator":"==",
            "value":"management-dashboard"
         }
      ]
   }
]
```
