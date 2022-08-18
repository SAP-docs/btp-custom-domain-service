<!-- loiob43e502e71f446fd96b906dfee12a131 -->

# Deactivate Custom Domains

Use the Cloud Foundry CLI to deactivate custom domains that you temporarily no longer want to use. As a result, a secure connection to applications that use those custom domains can be established only on their default domain.



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Deactivate the custom domains:

    ```
    cf custom-domain-deactivate <Custom Domain> <Custom Domain2> ...
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-deactivate *.applications.example.com
    > ```

    > ### Caution:  
    > -   If you deactivate a custom domain with client authentication, make sure to download the list of trusted certificates before you deactivate it. To do so, use the command: `cf custom-domain-show-trusted-certificates *.applications.example.com trustedCertificates.pem`.
    > 
    > -   Deactivating custom domains also deactivates client authentication for those domains. When reactivating a custom domain, client authentication is **not** automatically reactivated. To activate client authentication, see [Adding Trusted Certificates for Client Authentication to a Custom Domain](../20-Configuration/adding-trusted-certificates-for-client-authentication-to-a-custom-domain-a85e3c4.md).

4.  Check the deactivation status:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment the custom domain status is listed as deactivated, it can take until the next day to process the deactivation. The timezone depends on the region of your Cloud Foundry environment.


**Related Information**  


[Remove Custom Domains](remove-custom-domains-aea379a.md "Use the Cloud Foundry CLI to remove custom domains and certificates that you no longer want to use. As a result, any applications that use those custom domains can be reached only on their default domain.")

[Deactivate Client Authentication](deactivate-client-authentication-c397fc7.md "Use the Cloud Foundry CLI to deactivate client authentication for specific custom domains. As a result, your applications under those domains can be accessed without the need of client authentication.")

