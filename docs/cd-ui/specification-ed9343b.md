<!-- loioed9343ba00ea495ba84665e269eafcf3 -->

# Specification

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



</dd><dt><b>

Auditlog message process

</b></dt>
<dd>

All identities are scanned and if the server certificate expiration info has a severity equal to `high` or `critical`, an auditlog message is created. The expiration configuration of the landscape configuration is used.

For TLS configuration trust warning messages, all TLS configurations are scanned and if the trusted CA certificate expiration information has a severity equal to `high` or `critical` for one of the trusted CA certificates, an auditlog message is created. If more than one trusted CA certificate has expiration warnings, only one message is created for one TLS configuration. The trusted CA expiration configuration of the landscape configuration is used.

For TLS configuration ciphersuites warnings, all TLS configurations are scanned for ciphersuites warnings and the first owner \(tenant\) of the TLS configuration is used for the auditlog message. The HAProxy ciphersuites configuration \(exports\) of the landscape configuration is used to check the TLS configurations.

The auditlog message is created with the following information:

-   username: `SYSTEM`

-   tenant: The tenant of the identity or TLS configuration.

-   IP address: The IP address of the running container VM.

-   message: The JSON message as a string.




</dd>
</dl>

