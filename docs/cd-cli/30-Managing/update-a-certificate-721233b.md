<!-- loio721233b8efcf401094778a78f1bf2a66 -->

# Update a Certificate

If a certificate for your custom domains expires or you want to replace a certificate, use the Cloud Foundry CLI to upload and activate a new one that's based on a new certificate signing process.



## Procedure

1.  Create a new certificate signing request by following the steps in [Create a Certificate Signing Request](../20-Configuration/create-a-certificate-signing-request-ce1c42b.md).

    > ### Note:  
    > To keep high security standards, it is required to create a new key when updating a certificate.

2.  Upload your signed certificate:

    ```
    cf custom-domain-upload-certificate-chain <New Key Name> <New Filename>.pem
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-upload-certificate-chain myNewKey newCertificateChain.pem
    > ```

    The parameter `myNewKey` represents the new key that you created in the first step [Create a Certificate Signing Request](../20-Configuration/create-a-certificate-signing-request-ce1c42b.md).

    > ### Note:  
    > -   If your certificate authority sends you a PKCS\#7 file in the PEM format \(file content begins with "-----BEGIN PKCS7-----"\), run the following command to convert it to the required PEM-encoded X.509 certificate list: `openssl pkcs7 -in newCertificateChain.pem -inform PEM -out newCertificateChain.pem -outform PEM -print_certs`.
    > 
    > -   If you don't have OpenSSL, you must download and install it. You can find a download link at: [https://www.openssl.org/source/](https://www.openssl.org/source/)

3.  Activate the uploaded certificate for your custom domains:

    ```
    cf custom-domain-activate <New Key Name> <Custom Domain> <Custom Domain2> ...
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-activate myNewKey *.applications.example.com
    > ```

    > ### Note:  
    > Activating the domain with the new certificate and key automatically deactivates the old key and certificate. The old key is not deleted.

4.  Check the status of the activation process:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment the custom domain status is listed as activated, it can take until the next day to process the activation. The timezone depends on the region of your Cloud Foundry environment.

5.  Delete the old key:

    ```
    cf custom-domain-delete-key <Key Name>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-delete-key myKey
    > ```

6.  Verify that the key has been deleted:

    ```
    cf custom-domain-list
    ```


