# ASM User Auth

This repository contains the ASM User Auth deployment for Anthos service mesh.

## Release Notes

*   release-1.2
   
    + v1.2.4

        - Improved XSRF cookie handling. The XSRF cookie is now proactively deleted after a successful authentication.
        - Improved Logs and messages based on XSRF cookie handling.

    +   v1.2.3

        - Upgraded the internal HTTP client library and improved DNS compatibility when making outgoing HTTP requests.

    +   v1.2.2

        -   Upgraded the internal HTTP client library.
            -   This fixes a known issue that could cause User Auth to freeze in very rare network situations.
        -   Made various internal improvements.

    +   v1.2.1

        -   Improved session cookie security.
        -   Enabled extended logging.

    +   v1.2.0

        -   Updated `user-auth-config` for new binary configuration.
        -   Added `attributeMapping` field in UserAuthConfig for custom claims
            mapping from the original IDToken.

*   release-1.1

    +   v1.1.0

        -   Upgraded kpt to v1.0.
        -   Added the `proxy` field in the UserAuthConfig for http proxy
            support.
        -   Fixed a bug of the `certificateAuthorityData` field in the
            UserAuthConfig not working correctly.

*   release-1.0

    +   v1.0.1

        -   Added the `proxy` field in the UserAuthConfig for http proxy
            support.
        -   Fixed a bug of the `certificateAuthorityData` field in the
            UserAuthConfig not working correctly.

    +   v1.0.0

        -   GA Launch.
        -   Store client credentials in K8s secret.

*   release-0.1

    -   Preview Launch.

## User Guide

* [kpt pkg guide](./pkg/README.md)
* [User Auth User Guide](https://cloud.google.com/service-mesh/docs/security/end-user-auth)
