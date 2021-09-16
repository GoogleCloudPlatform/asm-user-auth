# ASM User Auth Kpt package

## Description

Kpt v1.0 package for ASM User Auth.

## Setters

-   `issuer-uri`: OAuth2 IDP URI.
-   `client-id`: ClientID configured in OAuth2 IDP, must be base64 encoded.
-   `client-secret`: ClientSecret configured in OAuth2 IDP, must be base64
    encoded.
-   `image`: The UserAuth image. Default:
    `gcr.io/gke-release/ais:hybrid_identity_charon_20210629_RC00`.
-   `secret-name`: The K8s secret UserAuth reads from. Default:
    `"oauth-secret"`.
-   `secret-namespace`: The namespace of the secret above. Default:
    `"asm-user-auth"`.
-   `redirect-host`: Redirect URI hostname for OAuth2 OIDC. Default: `""`.
-   `redirect-path`: Redirect URI path for OAuth2 OIDC. Default:
    `"/_gcp_asm_authenticate"`.
-   `jwt-audience`: Output JWT Audience field name from UserAuth. Default:
    `"test_audience"`.
-   `ca-cert`: Base64 encoded ODIC IDP root CA certificate in pem format. If it
    is `""`, User Auth will use the system default root CA certs. Default: `""`.
-   `scopes`: Comma-separated list of identifiers used to specify what access
    privileges are being requested in addition to "openid" scope, e.g.
    "groups,allatclaim". Default: `""`.
-   `groupsClaim`: Name of the claim in the OIDC ID Token that holds the user's
    group information. Default: `""`.
-   `hosts`: Array of hosts that whitelisted by UserAuth. Default: `"*"`.

## Instruction

1.  Use `kpt fn eval --image gcr.io/kpt-fn/apply-setters:v0.2 --` followed by
    `setter=value` to set the custom values.

    **IMPORTANT** Setters with no default values must be set before apply, e.g.
    `issuer-uri`, `client-id`, `client-secret`.

    Example:

    ```shell
    kpt fn eval pkg --image gcr.io/kpt-fn/apply-setters:v0.2 -- \
    client-id="ZmFrZS5hcHBzLmdvb2dsZXVzZXJjb250ZW50LmNvbQ==" \
    client-secret="ZmFrZXNlY3JldA==" \
    issuer-uri="https://issuer.dummy.com"
    ```

2.  Apply CRD then the rest of the pkg.

    ```shell
    # Remove the potential alpha version CRD if exists.
    kubectl delete crd userauthconfigs.security.anthos.io
    kubectl apply -f ./pkg/asm_user_auth_config_v1beta1.yaml
    kubectl apply -f ./pkg
    ```
