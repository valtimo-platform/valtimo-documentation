# Notes

## Access control

Access to the case notes can be configured through access control. More information about access control can be found [here](https://docs.valtimo.nl/features/access-control).

### Resources and actions

<table><thead><tr><th width="329">Resource type</th><th width="143">Action</th><th>Effect</th></tr></thead><tbody><tr><td><code>com.ritense.note.domain.Note</code></td><td><code>view_list</code></td><td>Allows viewing notes.</td></tr><tr><td></td><td><code>create</code></td><td>Allows creating a note</td></tr><tr><td></td><td><code>modify</code></td><td>Allows modifying a note</td></tr><tr><td></td><td><code>delete</code></td><td>Allows deleting a note</td></tr></tbody></table>

### Examples

<details>

<summary>Permission to view all notes</summary>

<pre class="language-json" data-overflow="wrap"><code class="lang-json">{
<strong>    "resourceType": "com.ritense.note.domain.Note",
</strong>    "action": "view_list",
    "conditions": []
}
</code></pre>

</details>

<details>

<summary>Permission to delete notes created by the logged-in user</summary>

{% code overflow="wrap" %}
```json
{
   "resourceType": "com.ritense.note.domain.Note",
   "action": "delete",
   "conditions": [
      {
         "type": "field",
         "field": "createdByUserId",
         "operator": "==",
         "value": "${currentUserIdentifier}"
      }
   ]
}
```
{% endcode %}

</details>
