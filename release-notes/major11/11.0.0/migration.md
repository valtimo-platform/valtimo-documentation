# Migration

This page describes how to update Valtimo from the previous version to the current.

* **Change in Recipient.Type values**

  Scope: back-end

  To meet coding standards, the Enum values of ```com.ritense.valtimo.contract.mail.model.value.Recipient.Type``` have been changed to all uppercase.
  References to these Enum values should be changed in implementations:
    - Change uses of Type.To to Type.TO
    - Change uses of Type.Cc to Type.CC
    - Change uses of Type.Bcc to Type.BCC

* **Rename application property valtimo.jwt.secret**

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

* **Rename application property valtimo.jwt.tokenValidityInSeconds**

  Scope: back-end

    1. **Find valtimo.jwt.tokenValidityInSeconds**

       Find all occurrences of `valtimo.jwt.tokenValidityInSeconds` and rename them all
       to `valtimo.oauth.tokenValidityInSeconds`. This property is usually found in the `application.yml`.

    2. **Find `VALTIMO_JWT_TOKEN_VALIDITY_IN_SECONDS`**

       Find all occurrences of `VALTIMO_JWT_TOKEN_VALIDITY_IN_SECONDS` and rename them
       to `VALTIMO_OAUTH_TOKEN_VALIDITY_IN_SECONDS`. This environment variable can potentially be found in many
       different places such as:
        - `.env.properties` file inside the repository
        - AWS Parameter store
        - Kubernetes `.yaml` file

* **Breaking change 2/Deprecation 2**

  Scope: back-end/front-end

    1. **Step1**

       Description
    2. **Step2**

       Description
