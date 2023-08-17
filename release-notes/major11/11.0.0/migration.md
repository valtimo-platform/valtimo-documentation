# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Rename application property**

  Scope: back-end

    1. **Find valtimo.jwt.secret**

       Find all occurrences of `valtimo.jwt.secret` and rename them all to `valtimo.oauth.public-key`. This property is
       usually found in the `application.yml`.

    2. **Find `VALTIMO_JWT_SECRET`**

       Find all occurrences of `VALTIMO_JWT_SECRET` and rename them to `VALTIMO_OAUTH_PUBLIC_KEY`. This environment
       variable can potentially be found in many different places such as:
        - `.env.properties` file inside the repository
        - AWS Parameter store
        - Kubernetes `.yaml` file

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

    1. **Step1**

       Description
    2. **Step2**

       Description
