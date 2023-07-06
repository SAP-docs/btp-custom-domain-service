<!-- loio6d121719db98496c9e34b116e2118ab6 -->

# Auditing and Logging Information

You can monitor the certificate expiration information and TLS configuration warnings of your custom domain configuration.

Checking the Custom Domain Manager UI cannot be automated. One option is to have a scheduled task in the Custom Domain service, which writes special auditlog messages for all the known tenants. These auditlog messages can then be consumed by an application, which reads the auditlog with the help of the auditlog management API.


<dl>
<dt><b>

Auditlog Viewer

</b></dt>
<dd>

There is also a SaaS application for reading auditlog messages; the auditlog-viewer. For more details, see the [Audit Log Viewer for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/audit-log-viewer-for-cloud-foundry-environment).



</dd><dt><b>

Auditlog Management API

</b></dt>
<dd>

The auditlog management API allows you to read the tenant auditlog messages. You need a Cloud Foundry instance of the auditlog management service and standard plan to communicate with the auditlog management API. For detailed information, see [Audit Log Retrieval API Usage for Subaccounts in the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/audit-log-retrieval-api-usage-for-subaccounts-in-cloud-foundry-environment).

**Possible Auditlog Message Types**

-   There are different categories of Auditlog messages:

    -   audit.security-events

    -   audit.configuration

    -   audit.data-access

    -   audit.data-modification


-   The Custom Domain service uses only two message categories:

    -   audit.security-events: For security events like authentication, certificate expiration and TLS configuration issues.

    -   audit.configuration: For configuration changes such as setting trust and uploading a certificate.



**Filter possibilities**

The auditlog management API can only be filtered with the `time_from` and `time_to` keywords. Other filter options are not possible on the Request API level.



</dd>
</dl>

