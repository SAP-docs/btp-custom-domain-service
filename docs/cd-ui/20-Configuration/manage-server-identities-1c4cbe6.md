<!-- loio1c4cbe695bed435f80a748a143a8351e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Server Identities

A server identity is a list of custom domain SANs \(Subject Alternative Names\) and one or two server certificates that share the list of SANs. Create a new server certificate and a certificate signing request \(CSR\) to obtain a certificate for your domains from a trusted certificate authority. Use the secondary server certificate to rotate to a new one with an extended lifetime, or from a different CA. Use the rotation REST API to integrate with your on-premise or cloud-based automation, like ACME CERTBOT or other solutions that are able to handle CSR \(`PKCS#10 PEM`\) and certificate chains \(set of `X.509 PEM`\).



<a name="loio1c4cbe695bed435f80a748a143a8351e__prereq_opk_fm3_zsb"/>

## Prerequisites

In general, before creating the required server certificates, you need to create the TLS configurations for those server certificate activations.

However, if you create your first server certificate without having a corresponding TLS configuration, a default configuration is automatically created. It is important to note that this is true for only the first server certificate; subsequent certificates need to have a TLS configuration created first.



<a name="loio1c4cbe695bed435f80a748a143a8351e__context_h43_ywx_yhb"/>

## Context

Depending on what kind of Subject Alternative Name \(SAN\) you want to add to the CSR, you should either use a wildcard \(`*.<subdomain.example.com>`\) or the application hostname \(`<myapp.subdomain.example.com>`\) in your entries.

Your CA may add or remove SANs, depending on the kind of certificate product you’re purchasing. For instance, the value of your Common Name will most likely be added as the SAN.



## Procedure

1.  Create a server certificate and a certificate signing request \(CSR\) for one or multiple custom domains:

    1.  Choose the *Server Identities* tile.

    2.  Choose *Create* and enter a name for your server identity.

    3.  Next, choose the target environment. Decide for PaaS or SaaS; and then accordingly choose *PaaS \(Cloud Foundry\)* \(usually, chosen by default\) or *SaaS Subscriptions*.

    4.  In the *Select Custom Domains* pane, select one or more of the available domain names and choose *Next Step*.

    5.  Next, in the *Certificate Subject* pane, enter the required information in the fields and choose *Next Step*.

        > ### Note:  
        > None of them is mandatory \(we support server certificates without a subject name\).

    6.  In the *Key Configuration* pane, select the key type and choose *Next Step*.

    7.  Check the details on the *Summary* pane and choose *Finish*.


    > ### Note:  
    > You can view how much of your quota you have consumed in the information displayed below the title bar. As you activate certificates, the numbers next to *Quota Consumption:* will reflect this change.

2.  Select the server certificate that you created to expand the details section.

    To order and install your new server certificate, you have to first create the certificate signing request. You have to send this file to a trusted certificate authority of your choice to get it signed.

3.  Choose *Get Certificate Signing Request* to copy the content and create the .pem file. You can also paste the content into a web page of your CA, if available.

4.  On receiving the new server certificate and full certificate chain \(including the root CA\), choose *Upload Full Certificate Chain* to upload them.

    1.  In the *Add Certificate* section, insert the certificate chain into the text field and choose *Next*.

    2.  Check the certificate and choose *Next*.

    3.  Confirm that the certificate is correct and click *Finish*.


5.  Finally, you have to activate your new server certificate.

    This activation has to be done for one or more of the certificate's SANs and the TLS configuration of your choice. The activation can be modified or removed at any time and takes a few minutes until it is effective in the landscape load balancer. Any corresponding SaaS routes are also automatically activated.

    1.  In the details pane, choose *Activate*.

    2.  Select the certificate that you want to activate and choose *Next*.

    3.  Select the SANs that you want to activate and choose *Next*.

    4.  Select the desired TLS configuration and choose *Next*.

    5.  Confirm the activation and choose *Finish*.





<a name="loio1c4cbe695bed435f80a748a143a8351e__result_bcg_j2z_cqb"/>

## Results

The list of server certificates created are displayed and as long as they are active, cannot be deleted. Inactive certificates can be deleted by using the *Delete* button.

You can use the *Activate* button to activate additional SANs or change the TLS configuration for an already activated SAN. Activated SANs can also be deleted by choosing :wastebasket:\(Delete\).

