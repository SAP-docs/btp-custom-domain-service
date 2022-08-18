<!-- loio5289f69c1119482ea3bece786553c692 -->

# Manage Trusted Certificates for Client Authentication

To manage client authentication, use the Cloud Foundry CLI to add or remove certificates to or from the list of trusted certificates.



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Download the list of trusted certificates as a .pem file:

    ```
    cf custom-domain-show-trusted-certificates <Custom Domain> <Filename>.pem
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-show-trusted-certificates *.applications.example.com trustedCertificates.pem
    > ```

    > ### Note:  
    > The file is downloaded to the folder where you executed the command, for example: `C:\Users\YourUsername`.

4.  Add to or remove certificates from the list of trusted certificates.

5.  Upload the updated list of trusted certificates:

    ```
    cf custom-domain-enable-client-authentication <Filename>.pem <Custom Domain> <Custom Domain2> ...
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-enable-client-authentication trustedCertificatesUpdatedList.pem *.applications.example.com
    > ```

    > ### Caution:  
    > This command overwrites the existing list of trusted certificates. The lists are not merged.

6.  Check the list of trusted certificates for your domain:

    ```
    cf custom-domain-show-trusted-certificates <Custom Domain>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-show-trusted-certificates *.applications.example.com
    > ```

7.  Check the activation process:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment that client authentication is listed as activated, it can take until the next day to process the activation. The timezone depends on the region of your Cloud Foundry environment.

    > ### Remember:  
    > Client authentication is turned on by uploading trusted certificates and turned off by deleting them.


