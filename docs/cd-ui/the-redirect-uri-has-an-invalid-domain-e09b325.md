<!-- loioe09b325cad9b4c65ac96cda71c775543 -->

# The redirect\_uri has an invalid domain



<a name="loioe09b325cad9b4c65ac96cda71c775543__section_g4b_ck4_hdc"/>

## Scenario

When accessing an application using a custom domain in Cloud Foundry, you get the following error message:

`The redirect_uri has an invalid domain`



<a name="loioe09b325cad9b4c65ac96cda71c775543__section_h4b_ck4_hdc"/>

## Reason

The reason for this error is that the custom domain is missing from the *redirect-uris* parameter of the application's security descriptor file.

-   Specify the custom domain in the redirect-uris parameter of the xs-security.json file.



<a name="loioe09b325cad9b4c65ac96cda71c775543__section_j4b_ck4_hdc"/>

## Solution

**Specify the custom domain in the redirect-uris parameter of the xs-security.json file.**

The required custom domain needs to be maintained in the application security descriptor file \(xs-security.json\). In the syntax of the application security descriptor file, specify the custom domain in the *redirect-uris* parameter.

```
 
```

In the syntax of the application security descriptor file, specify the custom domain in the redirect-uris parameter.

> ### Example:  
> ```
> "oauth2-configuration": {     "redirect-uris": ["https://myapp.cfapps.eu10.hana.ondemand.com/**","https://*.mydomain.com/**"] }
> ```



For more information about the `xs-security.json` file, see [Application Security Descriptor Configuration Syntax](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/517895a9612241259d6941dbf9ad81cb.html).

