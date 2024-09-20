# Configuring access control


Before you can use access control with dashboards you need to enable the feature toggle in your `application.yml`.
```
valtimo:
    authorization:
            dashboard:
                enabled: true
```
Without this enabled access control will not work for your dashboards.



## Expanding your existing PBAC autodeployment

For your new dashboards you will need to set up som permissions. For example, you want someone with the role of Admin to be able to see all dashboards. 
Then you would expand their role permissions with the following:

```
[
    {
        "resourceType": "com.ritense.dashboard.domain.Dashboard",
        "action": "view",
        "roleKey": "ROLE_ADMIN",
        "conditions": []
    },
    {
        "resourceType": "com.ritense.dashboard.domain.Dashboard",
        "action": "view_list",
        "roleKey": "ROLE_ADMIN",
        "conditions": []
    }
]
```


### Adding conditions

Say for instance that you want someone with a user role to only see 1 of the dashboards you have created, then it would look like the following:

```
[
    {
        "resourceType": "com.ritense.dashboard.domain.Dashboard",
        "action": "view",
        "roleKey": "ROLE_USER",
        "conditions": [
            {
                "type": "field",
                "field": "key",
                "operator": "==",
                "value": "loans-dashboard"
            }
        ]
    },
    {
        "resourceType": "com.ritense.dashboard.domain.Dashboard",
        "action": "view_list",
        "roleKey": "ROLE_USER",
        "conditions": [
            {
                "type": "field",
                "field": "key",
                "operator": "==",
                "value": "loans-dashboard"
            }
        ]
    }
]
```

We make sure the value matches the key of the dashboard you've created.
