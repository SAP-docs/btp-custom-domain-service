<!-- loio1c6c729595f144d9a0bec1b4e2ef1299 -->

# Configuring Custom Domains

To make sure that your domain is trusted and all application data is protected, you must first set up secure TLS/SSL communication. Then, make your application reachable via the custom domain and route traffic to it.



<a name="loio1c6c729595f144d9a0bec1b4e2ef1299__prereq_m3d_kdm_3gb"/>

## Prerequisites

-   Download and install the Cloud Foundry command-line interface \(CLI\), see [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/4ef907afb1254e8286882a2bdef0edf4.html "Download and set up the Cloud Foundry Command Line Interface (cf CLI) to start working with the Cloud Foundry environment.") :arrow_upper_right:.

-   Download and install the Cloud Foundry CLI plugin for custom domains, see [Custom Domain Plugin for the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/1832fcd1eec9415694de50f620e5a522.html "The Custom Domain CLI plugin provides functions for creating private keys and certificate signing requests, as well as additional commands for managing your custom domains.") :arrow_upper_right:.




## Procedure

1.  [Creating Custom Domains with TLS/SSL Server Authentication](creating-custom-domains-with-tls-ssl-server-authentication-afeb1e7.md)

    1.  [Create Custom Domains](create-custom-domains-2ab0040.md)

    2.  [Create a Certificate Signing Request](create-a-certificate-signing-request-ce1c42b.md)

    3.  [Upload and Activate the Signed Certificate](upload-and-activate-the-signed-certificate-908a691.md)

    4.  [Configure the DNS for a Custom Domain](configure-the-dns-for-a-custom-domain-da9b54e.md)

    5.  [Map Your Own Application to a Custom Domain](map-your-own-application-to-a-custom-domain-d898407.md)

    6.  [Test the Custom Domain](test-the-custom-domain-febe99c.md)


2.  \(Optional, only if your using client authentication\) [Adding Trusted Certificates for Client Authentication to a Custom Domain](adding-trusted-certificates-for-client-authentication-to-a-custom-domain-a85e3c4.md)

3.  \(Optional, only if you want to share your custom domains\) [Sharing Custom Domains](sharing-custom-domains-8ecabca.md)


