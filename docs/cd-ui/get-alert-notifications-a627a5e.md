<!-- loioa627a5e3568a4518a02cb4300b7722e5 -->

# Get Alert Notifications

Specific critical issues generate custom domain alert notifications.



## **Alert Types**

-   An activated server certificate is going to expire or has already expired.

-   A TLS configuration used by an activated server certificate contains a trusted CA certificate, which is going to expire or has already expired.

-   A TLS configuration used by an activated server certificate contains a deprecated or unsupported cipher suite.


No alert notifications are generated for inactive server certificates or unused TLS configurations.



<a name="loioa627a5e3568a4518a02cb4300b7722e5__section_vks_mgm_lzb"/>

## **Certificate Expiration Alert Thresholds**

If a server certificate reaches 85% of its lifetime, a critical alert is generated the first time.

> ### Example:  
> A server certificate has a validity of 1 year. The first alert is generated 55 days before the expiration date.

If a trusted CA certificate reaches 85% of its lifetime, a critical alert is generated the first time.

> ### Example:  
> A trusted CA certificate has a validity of 20 years. The first alert is generated 3 years before the expiration date.



<a name="loioa627a5e3568a4518a02cb4300b7722e5__section_gml_qgm_lzb"/>

## **Alert Schedule**

Custom domain alert notifications are generated on a daily basis.

You will get notifications for the same critical issues every day, until the underlying problem is solved, namely:

-   The expiring or expired server certificate is replaced or deactivated.

-   The expiring or expired trusted CA certificate is removed from the TLS configuration.

-   The TLS configuration is not in use anymore.

-   The deprecated cipher suite is removed from the TLS configuration.


**Related Information**  


[SAP Alert Notification for SAP BTP: Initial Setup](https://help.sap.com/docs/alert-notification/sap-alert-notification-for-sap-btp/initial-setup?version=Cloud)

