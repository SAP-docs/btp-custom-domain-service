<!-- loio422daa85579241368985de3099390a94 -->

# Certificates are Invalid: Make Sure that you Provide the Complete Certificate Chain



<a name="loio422daa85579241368985de3099390a94__section_wtf_tj4_hdc"/>

## Scenario

You tried to upload a certificate and get the following error message:

```
Certificates are invalid: Make sure that you provide the complete certificate chain.
```

```

```



<a name="loio422daa85579241368985de3099390a94__section_xtf_tj4_hdc"/>

## Reason

You uploaded a single certificate instead of the full certificate chain. A certificate chain is an ordered list of certificates, containing an TLS/SSL certificate and certificate authority \(CA\) certificates, that enable the receiver to verify that the sender and all certificate authorities are trustworthy.



<a name="loio422daa85579241368985de3099390a94__section_ytf_tj4_hdc"/>

## Solution



### Create the certificate chain file

Depending on your certificate authority and the service that it provides, you might have to create the certificate chain file yourself. You can do this by concatenating single certificate files into one certificate chain in the .pem format. Make sure to do this in the correct order starting from the root CA.

> ### Example:  
> Your certificate authority sends you the following files:
> 
> -   Root CA certificate: *root-ca.crt*
> -   Intermediate CA certificate: *intermediate-ca.crt*
> -   Your TLS/SSL wildcard certificate: *wildcard-mydomain-com.crt*
> 
> Depending on your certificate authority, the number of intermediate certificates may vary.



### Create the certificate chain file

1.  Copy the content of the root CA certificate file into a text editor.
2.  Add the content of the intermediate CA certificate to the text file, below the root CA certificate \(below -----END CERTIFICATE-----\).
3.  Add the content of the final certificate to the text file below the intermediate CA certificate \(below -----END CERTIFICATE-----\).
4.  Save the file with the .pem suffix.
5.  Try the certificate upload again with the newly created certificate chain file.

