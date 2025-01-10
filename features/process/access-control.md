# Access control

Access to the processes can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="329">Resource type</th><th width="143">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.valtimo.camunda.domain.CamundaExecution</code></td><td><code>create</code></td><td>Allows creating an execution for a process definition.</td></tr><tr><td><code>com.ritense.valtimo.camunda.domain.CamundaProcessDefinition</code></td><td>-</td><td>-</td></tr></tbody></table>

Process definitions have no actions currently. As a result, they can only be used as part of container conditions. See the example [here](access-control.md#permission-to-start-a-process-for-one-specific-process-definition) on how to use this.

### Examples

#### Permission to start a process for one specific process definition

<pre class="language-json"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.valtimo.camunda.domain.CamundaExecution",
</strong>    "action": "create",
    "conditions": [
        {
            "type": "container",
            "resourceType": "com.ritense.valtimo.camunda.domain.CamundaProcessDefinition",
            "conditions": [
                {
                    "type": "field",
                    "field": "key",
                    "operator": "==",
                    "value": "evenementenvergunning"
                }
            ]
        }
    ]
}
</code></pre>
