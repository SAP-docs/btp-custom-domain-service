<!-- loio5e983f4b646a4d25aa1fce5c4d77e7cc -->

# Automated Server Certificate Rotation

In 2025, CA/Browser Forum Ballot SC081v3 introduced a schedule of reducing validity and data reuse periods for TLS server certificates.



Public CAs will issue shorter maximum lifetimes over the next years, beginning with the given start dates:

-   March 2026: 200 days

-   March 2027: 100 days

-   March 2029: 47 days


Concrete public CAs may decide to start earlier and with even shorter lifetimes.

A manual rotation of custom domain certificates will become hard to handle.

Custom Domain Manager provides a new REST API that allows you to rotate a server identity's server certificate. The API can be integrated into a customer's on-premise or cloud-based Certificate Lifecycle Management system, like an ACME CERTBOT. The Custom Domain service does not manage customer DNS records or connect to public CAs on behalf of customers.



## Implementation

The REST API provides two main functions:

-   Create a new key and CSR.

-   Upload the new server certificate with the CA chain.


ACME clients like CERTBOT allow you to consume such APIs with some programmatical effort; for example, in a BASH or PYTHON script.

For a more sophisticated integration, the REST APIs return JSON objects with details about the current situation, the rotation status, and the certificates involved.

*REST API Endpoints*

The following API endpoints are used to start and complete a rotation, and to get the status of the rotated certificate in Custom Domain Manager.

-   `<region>.customdomain.cloud.sap/api/v3/identities/<identity>/rotation/<algorithm>/initialize`

-   `<region>.customdomain.cloud.sap/api/v3/identities/<identity>/rotation/<algorithm>/finalize`

-   `<region>.customdomain.cloud.sap/api/v3/identities/<identity>/rotation/<algorithm>/status`


where:

-   <region\> is the region where Custom Domain Manager is running; for example, `eu10`, which is not necessarily the same as the CF landscape where the certificate resides; for example, `eu10-005`.

-   <identity\> is the technical identifier of the server identity holding the server certificate that needs to be rotated. You can get it from the *Identity Information* \> *Property* \> *Identity* field.

-   <algorithm\> is the key type and size of the new server certificate. Currently, `rsa2048`, `rsa3072`, and `rsa4096` are supported.


All endpoints require SAP BTP authentication; either by the SAP Authorization and Trust Management service \(XSUAA\) or the Cloud Foundry User Account and Authentication \(UAA\)-based.

With `/initialize`, a new key of type and size given by the `<algorithm>` is generated, and its CSR is returned once the key generation is done. Multiple calls may be needed to complete.

With `/finalize`, the new certificate and CA chain can be uploaded. The new server certificate is activated with the same set of SANs and the same TLS configurations as before.

With `/status`, the status of an identity, a new CSR, and the certificate activation can be retrieved, while the actual status differs and depends on the rotation phase.



## Rules

Only one server certificate per server identity can be created and rotated by using this API.

The following situations are supported:

1.  There is only one CSR in place \(this is the default situation for a newly created server identity\).

    1.  `/initialize` uses the existing CSR.

    2.  `/finalize` creates an inactive server certificate.

    3.  The activation must be performed manually.


2.  There is no CSR or server certificate in place.

    1.  `/initialize` creates a CSR.

    2.  `/finalize` creates an inactive server certificate.

    3.  The activation must be performed manually.


3.  There is one activated server certificate in place.

    1.  `/initialize` creates a successor CSR for the activated server certificate.

    2.  `/finalize` uploads the successor server certificate and replaces the successor CSR.

    3.  `/finalize` activates the successor server certificate, exactly as its predecessor.

    4.  The predecessor server certificate stays in the `inactive` status.


4.  There is one activated and one inactive server certificate in place.

    1.  `/initialize` deletes the inactive server certificate.

    2.  `/initialize` creates a successor CSR for the activated server certificate.

    3.  `/finalize` uploads the successor server certificate and replaces the successor CSR.

    4.  `/finalize` activates the successor server certificate, exactly as its predecessor.

    5.  The predecessor server certificate stays in the `inactive` status.


    The following situations are not supported, but can be solved.

5.  There is one inactive server certificate in place. Solutions:

    1.  Manually delete the server certificate. Situation 2 is now followed.

    2.  Manually activate the server certificate. Situation 3 is now followed.


6.  There are two activated server certificates in place. Solution:

    1.  Manually reactivate one server certificate and take over the SAN activations of the second one. The second server certificate is then inactive. Situation 4 is now followed.


7.  There are two inactive server certificates in place. Solution:

    1.  Manually activate the server certificate that should be rotated. Situation 4 is now followed.



> ### Note:  
> Even with an automation in place, it's recommended to start the rotation with sufficient remaining lifetime. This ensures that there is enough time for corrections; for example, during the holiday season.
> 
> -   200 days lifetime: Rotate after 150 days \(50 days left\)
> 
> -   100 days lifetime: Rotate after 50 days \(50 days left\)
> 
> -   47 days lifetime: Rotate after 17 days \(30 days left\)
> 
> 
> In addition, certificate expiration monitoring \(for example, by using SAP BTP CALM\) is strongly recommended. Do not rely on automation only.

