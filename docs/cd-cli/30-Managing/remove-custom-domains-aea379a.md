<!-- loioaea379ad5ac6466e8c6603b799e04e2b -->

# Remove Custom Domains

Use the Cloud Foundry CLI to remove custom domains and certificates that you no longer want to use. As a result, any applications that use those custom domains can be reached only on their default domain.



<a name="loioaea379ad5ac6466e8c6603b799e04e2b__prereq_ekh_3ym_ngb"/>

## Prerequisites

Deactivate the custom domains that you want to remove: [Deactivate Custom Domains](deactivate-custom-domains-b43e502.md).



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Delete the key of the custom domains that you want to remove:

    ```
    cf custom-domain-delete-key <Key Name>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-delete-key myKey
    > ```

    > ### Note:  
    > You must wait until the deactivation process has finished before you try to delete the key, otherwise, you'll see the message: ***"Key cannot be deleted because it is still in use."***

4.  Verify that the key has been deleted:

    ```
    cf custom-domain-list
    ```

5.  Remove the custom domain:

    ```
    cf delete-domain <Custom Domain>
    ```

    ```
    cf delete-domain applications.example.com
    ```

    > ### Caution:  
    > -   Deactivate the custom domains that you want to delete first, before removing them. You must delete each domain separately.
    > 
    > -   Deleting the custom domain will automatically delete the routes from applications to that domain.
    > 
    >     If you used a custom domain for a SaaS application, you have to manually remove the route. To do this, use the command: `cf custom-domain-unmap-route <Application Hostname><Custom Domain>`

    > ### Note:  
    > If you delete a domain that is used along other domains under one certificate, you can still use the certificate for the remaining domains. If you wish to create a new certificate for the remaining domains, please repeat the steps described in [Creating Custom Domains with TLS/SSL Server Authentication](../20-Configuration/creating-custom-domains-with-tls-ssl-server-authentication-afeb1e7.md).

6.  Confirm the deletion process by typing: ***y***.

7.  Verify that the domain has been deleted:

    ```
    cf domains
    ```


**Related Information**  


[Deactivate Custom Domains](deactivate-custom-domains-b43e502.md "Use the Cloud Foundry CLI to deactivate custom domains that you temporarily no longer want to use. As a result, a secure connection to applications that use those custom domains can be established only on their default domain.")



