<!-- loiod9f22421bdeb4222a484c4fcadf8bee7 -->

# Key Does not Exist



<a name="loiod9f22421bdeb4222a484c4fcadf8bee7__section_d2f_xj4_hdc"/>

## Scenario

You tried to upload an existing certificate with the command *cf custom-domain-upload-certificate-chain* and get the following error message:

```
Key does not exist.



```



<a name="loiod9f22421bdeb4222a484c4fcadf8bee7__section_e2f_xj4_hdc"/>

## Reason

There are two possible reasons.

-   When executing the cf custom-domain-upload-certificate-chain <mykey\> <certificatechain.pem\> command, you chose the wrong key for the certificate or had a typo in the <mykey\> parameter.

-   You've uploaded an existing certificate including a private key that has not been created with the Custom Domain service CLI.



<a name="loiod9f22421bdeb4222a484c4fcadf8bee7__section_rrj_5np_fdc"/>

## Solution



### Create a CSR with a key from the Custom Domain CLI

Due to security reasons and the way in which the Custom Domain service operates, it's mandatory for uploaded certificates to be based on a private key and a certificate signing request \(CSR\) that has been created with the Custom Domain service CLI.

To solve the issue of uploading a certificate that hasn't been created with the CLI, create a new key and a certificate signing request with the Custom Domain CLI. Then you have to get this CSR signed and upload the signed certificate for your custom domain\(s\). To do that, make yourself familiar with the [prerequisites](https://help.sap.com/docs/CUSTOM_DOMAINS/74af813c7ee2457cb5eddca0cc70a0c1/48cdbe7a64f3475586dc2f4d11c5603c.html?version=Cloud) of the Custom Domain service and follow the official [Help Portal documentation of the Custom Domain service](https://help.sap.com/docs/CUSTOM_DOMAINS?version=Cloud).



### Check your command syntax when uploading a certificate

If there is no typo in the key name, make sure that you are using the same key name that you used when creating the certificate signing request \(CSR\) with the cf custom-domain-create-key command. Use the following command to list the keys and corresponding domain\(s\):

```
cf custom-domain-list
```

