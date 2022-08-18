<!-- loioce1c42b909b34eedafe1f9eecc15ddfa -->

# Create a Certificate Signing Request

Use the Cloud Foundry CLI to create a private key and a certificate signing request \(CSR\) to obtain a certificate for your custom domains from a trusted certificate authority.



<a name="loioce1c42b909b34eedafe1f9eecc15ddfa__context_h43_ywx_yhb"/>

## Context

Depending on what kind of Subject Alternative Name \(SAN\) you want to add to the CSR, you should either use a wildcard \(`*.<subdomain.mydomain.com>`\) or the application hostname \(`<myapp.subdomain.mydomain.com>`\) in your commands.

Your CA may add or remove SANs, depending on the kind of certificate product you are purchasing. For instance, the value of your Common Name will most likely be added as SAN.



## Procedure

1.  Create a private key and certificate signing request \(CSR\) for one or multiple custom domains:

    ```
    cf custom-domain-create-key <mykey> <"CN=mycloud, EMAIL=admin@myorganization.com, O=myorganization, C=mycountry"> "*.<subdomain.mydomain.com>" "<myapp.subdomain.mydomain2.com>" ...
    ```

    > ### Caution:  
    > Every custom domain that uses that key must be added here. There is no option to add a custom domain to an existing key at a later point of time.

    > ### Restriction:  
    > -   Only the following parameters are supported. Only the CN parameter of the command is required, the other parameters are optional.
    > 
    >     -   CN = Common Name – a subject for the certificate request, in this example: **mycloud**.
    > 
    >     -   EMAIL = Email – This cannot be a personal email address, but should be an administrative email address; for example: **admin@company.com**
    > 
    >     -   OU = Organizational Unit, for example: **IT Department**.
    > 
    >     -   O = Organization - company name, for example: **SAP**.
    > 
    >     -   L = Locality - city full name, for example: **Portsmouth**.
    > 
    >     -   ST = State - state or province name, for example: **Hampshire**.
    > 
    >     -   C = Country - two-digit code - for example: **GB**.

    > ### Note:  
    > -   If your certificate doesn't contain SANs after being signed, the Custom Domain service will use the value of the CN parameter to look for domains.
    > 
    > -   The domains that you specify in the command are added as a Subject Alternative Name to the certificate signing request.
    > 
    > -   The name of the key has to be unique and is later used to activate your custom domains.

2.  Download the certificate signing request:

    ```
    cf custom-domain-get-csr <mykey> <filename.pem>
    ```




<a name="loioce1c42b909b34eedafe1f9eecc15ddfa__result_e1b_cvs_dgb"/>

## Results

You have now successfully created a private key and a certificate signing request. You can find the .pem file in the folder where you executed the command. Send this file to a trusted certificate authority of your choice to get it signed.

