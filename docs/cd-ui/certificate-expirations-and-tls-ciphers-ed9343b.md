<!-- loioed9343ba00ea495ba84665e269eafcf3 -->

# Certificate Expirations and TLS Ciphers

All events like certificate expiration or TLS configuration warnings are from the `audit.security-events` message category.



## Security Message Type and Data

These kind of messages have no attributes, but only a message string.

You can parse the different events available as JSON objects in the security event message.


<dl>
<dt><b>

JSON object specification

</b></dt>
<dd>

You should be able to distinguish between a certificate and a TLS configuration warning. All security events are from the `CUSTOM_DOMAIN_WARNING` category.

The different JSON messages will have the following types, with different attributes:

> ### Sample Code:  
> ```
> - SERVER_CERTIFICATE
> - TLS_CONFIGURATION
> ```

Example of a certificate expiration warning:

> ### Sample Code:  
> ```
> {
>     "event": "CUSTOM_DOMAIN_WARNING",
>     "object":
>     {
>         "type": "SERVER_CERTIFICATE",
>         "guid": "The certificate guid",
>         "name": "The identity alias name"
>     },
>     "reason":
>     {
>         "expiring_server_certificate" {
>             "subject": "certificate subject DName",
>             "issuer": "certificate issuer DName",
>             "serialnumber": "certificate serialnumber",
>             "subject_alternative_names": [
>                 "domain.com",
>             ],
>             "valid_not_after": "The expire date of the certificate in UTC"
>         }
>     }
> }
> ```

Example of a TLS configuration ciphersuites warning:

> ### Sample Code:  
> ```
> {
>     "event": "CUSTOM_DOMAIN_WARNING",
>     "object":
>     {
>         "type": "TLS_CONFIGURATION",
>         "guid": "The tls configuration guid",
>         "name": "tls configuration name",
> 
>     },
>     "reason": {
>         "deprecated_ciphersuites": [
>             "ECDHE-RSA-AES128-SHA256",
>             "ECDHE-RSA-AES256-SHA384"
>         ]
>     }
> }
> ```

Example of a trusted CA certificates warning:

> ### Sample Code:  
> ```
> {
>     "event": "CUSTOM_DOMAIN_WARNING",
>     "object":
>     {
>         "type": "TLS_CONFIGURATION",
>         "guid": "The tls configuration guid",
>         "name": "tls configuration name",
>     },
>     "reason": {
>         "expiring_trusted_certificate": [
>             {
>                 "subject": "certificate subject name",
>                 "issuer": "certificate issuer DName",
>                 "serialnumber": "certificate serialnumber",
>                 "valid_not_after": "The expire date of the certificate in UTC"
>             }
>         ]
>     }
> }
> ```



</dd>
</dl>

