# ASM User Auth

This repository contains the ASM User Auth deployment for Anthos service mesh.

## Release Notes

*   release-1.2

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
