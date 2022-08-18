<!-- loioa85e3c414a4d4a9fb406215acb6bfce1 -->

# Adding Trusted Certificates for Client Authentication to a Custom Domain

Use client authentication to make your application more secure and grant individual access to your custom domains.



<a name="loioa85e3c414a4d4a9fb406215acb6bfce1__prereq_x34_b2k_3gb"/>

## Prerequisites

Create a custom domain with TLS/SSL server authentication; see [Creating Custom Domains with TLS/SSL Server Authentication](creating-custom-domains-with-tls-ssl-server-authentication-afeb1e7.md).



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Upload your list of trusted certificates and assign it to your custom domains:

    ```
    cf custom-domain-enable-client-authentication <Filename>.pem <Custom Domain> <Custom Domain2> ...
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-enable-client-authentication trustedCertificates.pem *.applications.example.com
    > ```

4.  Display the list of trusted certificates for your domain:

    ```
    cf custom-domain-show-trusted-certificates <Custom Domain> <Filename>.pem
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-show-trusted-certificates *.applications.example.com
    > ```

    > ### Note:  
    > To download a list of trusted certificates, type: `cf custom-domain-show-trusted-certificates *.applications.example.com trustedCertificates.pem`.

5.  Check the activation process:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment that client authentication is listed as activated, it can take until the next day to process the activation. The timezone depends on the region of your Cloud Foundry environment.


**Related Information**  


[Manage Trusted Certificates for Client Authentication](../30-Managing/manage-trusted-certificates-for-client-authentication-5289f69.md "To manage client authentication, use the Cloud Foundry CLI to add or remove certificates to or from the list of trusted certificates.")

[Deactivate Client Authentication](../30-Managing/deactivate-client-authentication-c397fc7.md "Use the Cloud Foundry CLI to deactivate client authentication for specific custom domains. As a result, your applications under those domains can be accessed without the need of client authentication.")

