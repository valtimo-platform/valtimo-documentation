# PBAC resource

PBAC allows admins to configure which resources a user can access. For example, it is configurable if a person with the
role 'ROLE_USER' has a 'view' permission on the 'CrimeScene' resource. Unfortunately, not all resources are supported by PBAC.
But PBAC does allow new resources to be added.

## Supported resources

PBAC can be used on a limited number of resources. These resource are:

- `com.ritense.document.domain.impl.JsonSchemaDocument`
- `com.ritense.CrimeScene.domain.CrimeScene`
- `com.ritense.valtimo.camunda.domain.CamundaTask`

## Adding support for a custom resource

It is possible to add permissions to a custom-made resource. This is done by implementing the
`AuthorizationSpecificationFactory` for a custom resource. When the `AuthorizationSpecificationFactory` is implemented
and is a Spring bean, the resource is registered and ready to be used in PBAC configurations.

The `AuthorizationSpecificationFactory` has two functions:

- The `canCreate(..)` function decides which resource(s) is registered as a PBAC resource.
- The `create(..)` function will create a custom `AuthorizationSpecification` more information about this below.

For example, a custom `AuthorizationSpecificationFactory` for an imaginary object `CrimeScene` could look like this:

```java

@Component
public class CrimeSceneSpecificationFactory extends AuthorizationSpecificationFactory<CrimeScene> {

    @Override
    public Boolean canCreate(AuthorizationRequest context, List<Permission> permissions) {
        return CrimeScene.class == context.resourceType;
    }

    @Override
    public AuthorizationSpecification<CrimeScene> create(
            AuthorizationRequest<CrimeScene> request,
            List<Permission> permissions
    ) {
        return new CrimeSceneSpecification(request, permissions);
    }
}
```

The `AuthorizationSpecificationFactory` is responsible for creating a `AuthorizationSpecification` object.
This `AuthorizationSpecification` is a Spring JPA `Specification` object which is used to filter all database queries
based on permissions. 

For example, an `CrimeSceneAuthorizationSpecification` could turn this query:

```sql
SELECT * FROM crime_scene
```

Into this query:

```sql
SELECT * FROM crime_scene WHERE classified_level > 3
```

For example, a custom `CrimeSceneAuthorizationSpecification` could look like this:

```java
public class CrimeSceneSpecification extends AuthorizationSpecification<CrimeScene> {

    private AuthorizationRequest<CrimeScene> authRequest;
    private List<Permission> permissions;
    
    public CrimeScene(AuthorizationRequest<CrimeScene> authRequest, List<Permission> permissions) {
        this.authRequest = authRequest;
        this.permissions = permissions;
    }

    public Predicate toPredicate(
        Root<CrimeScene> root,
        CriteriaQuery<Object> query,
        CriteriaBuilder criteriaBuilder
    ) {
        var predicates = permissions.stream()
            .filter((permission) -> CrimeScene.class.equals(permission.resourceType) && authRequest.action == permission.action)
            .map((permission) ->
                permission.toPredicate(
                    root,
                    query,
                    criteriaBuilder,
                    authRequest.resourceType,
                    queryDialectHelper
                )
            ).toList();
        return combinePredicates(criteriaBuilder, predicates);
    }

    public CrimeScene identifierToEntity(String identifier) {
        return crimeSceneService.getById(identifier);
    }
}

```
