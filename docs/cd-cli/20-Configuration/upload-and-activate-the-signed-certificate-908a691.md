<!-- loio908a691a2465493e8adaf36a9f21eff0 -->

# Upload and Activate the Signed Certificate

Use your signed certificate to activate secure communication between your application and clients.



<a name="loio908a691a2465493e8adaf36a9f21eff0__prereq_b1l_12c_kgb"/>

## Prerequisites

Create a certificate signing request, and verify that you have a signed certificate from a trusted certificate authority.



<a name="loio908a691a2465493e8adaf36a9f21eff0__context_ixj_dvy_1lb"/>

## Context

Upload the complete certificate chain in the .pem format. A certificate chain is an ordered list of certificates, containing an TLS/SSL certificate and certificate authority \(CA\) certificates, that enable the receiver to verify that the sender and all certificate authorities are trustworthy.

Depending on your certificate authority, you might have to create the certificate chain file yourself. This can be done by concatenating single certificate files to one certificate chain in the .pem format. See [Guided Answers - create a certificate chain file](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2437/actions/32393:36070:36072).



## Procedure

1.  Upload your signed certificate:

    ```
    cf custom-domain-upload-certificate-chain <Key Name> <Filename>.pem
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-upload-certificate-chain myKey certificateChain.pem
    > ```

    > ### Note:  
    > -   `myKey` refers to the key that you created for your custom domain in the previous steps.
    > 
    > -   If your certificate doesn't contain SANs after being signed, the Custom Domain service will use the value of the CN parameter to look for domains.
    > 
    > -   If your certificate authority sends you a PKCS\#7 file in the PEM format \(file content begins with "-----BEGIN PKCS7-----"\), run the following command to convert it to the required PEM-encoded X.509 certificate list: `openssl pkcs7 -in certificateChain.pem -inform PEM -out certificateChain.pem -outform PEM -print_certs`
    > 
    >     If you don’t have OpenSSL, you must download and install it. You can find a download link at: [https://www.openssl.org/source/](https://www.openssl.org/source/).

    > ### Restriction:  
    > -   We don’t support uploading existing certificates including a private key \(PFX, PKCS\#12\).
    > 
    > -   The certificate chain is valid only for the organization and the landscape on which it was generated and can’t be moved. The landscape represents the region: for example, **eu10.hana.ondemand.com** for Europe, **us10.hana.ondemand.com** for the United States, **ap10.hana.ondemand.com** for Asia-Pacific, and so on.

2.  Verify that the certificate has been uploaded and assigned to your key:

    ```
    cf custom-domain-show-certificates <Key Name>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-show-certificates myKey
    > ```

3.  Activate the uploaded certificate for your custom domains:

    ```
    cf custom-domain-activate <Key Name> "<Custom Domain>" "<Custom Domain2>" ...
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-activate myKey "*.applications.example.com"
    > ```

4.  Check the status of the activation process:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment the custom domain status is listed as activated, it can take until the next day to process the activation. The timezone depends on the region of your Cloud Foundry environment.


