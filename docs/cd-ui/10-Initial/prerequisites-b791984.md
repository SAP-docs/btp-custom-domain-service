<!-- loiob791984a063a48169b9e0b9af802f67e -->

# Prerequisites

Before configuring custom domains, you have to make some preliminary steps and fulfill a number of prerequisites.



<a name="loiob791984a063a48169b9e0b9af802f67e__section_e12_jfb_mgb"/>

## Choose and Acquire the Domain Names to Be Used by Your Applications

You have to come up with a list of custom domains and applications that you want to be served through them. For example, you may decide to have three custom domains for test, preview and production versions of your application:

-   test.example.com

-   preview.example.com

-   production.example.com


After configuring your custom domains, you can securely reach your application, for example "myapp" under the three domains:

-   myapp.test.example.com

-   myapp.preview.example.com

-   myapp.production.example.com


> ### Note:  
> -   You can also choose a separate domain for different countries, for example: **production.example.com**, **production.example.jp**, and **production.example.de**.
> 
> -   Domain names are owned by the customer, not by SAP BTP. Therefore, you have to buy any custom domain names from a registrar who sells domain names.



<a name="loiob791984a063a48169b9e0b9af802f67e__section_f12_jfb_mgb"/>

## Choose a TLS/SSL Certificate

To make sure that your domain is trusted and all your application data is protected, you have to get an appropriate TLS/SSL certificate from a Certificate Authority \(CA\). Determine the domains you want to be protected by this certificate. One certificate can be valid for a number of domains and subdomains but you can also use a dedicated certificate for each domain.

-   **Standard certificate** - A standard certificate protects one domain, for example. **www.example.com**.

-   **Wildcard certificate** - A wildcard certificate secures multiple applications of a domain, for example, **\*.example.com** covers any application under the domain **example.com**, like **myapp.example.com**, but not the domain **example.com** itself.

    This also works with subdomains, for example **\*.applications.example.com** covers any application under the subdomain **applications.example.com**, like **myapp.applications.example.com**, but not the subdomain **applications.example.com** itself.


> ### Note:  
> Certificates are owned by the customer, not by SAP BTP. Therefore, you have to get the required TLS/SSL certificates from a Certificate Authority \(CA\).

> ### Remember:  
> To connect to Cloud Foundry and any custom domain \(your own as well as those on SAP BTP, you have to be able to use the TLS Server Name Indication \(SNI\)\).



<a name="loiob791984a063a48169b9e0b9af802f67e__section_swb_b1v_lhb"/>

## Certificate Lifecycle Management

To make sure that a secure connection to your applications is maintained, use a certificate lifecycle management tool to monitor your certificates. You won't receive a warning from SAP BTP or the Custom Domain service if one of your certificates is about to expire.



<a name="loiob791984a063a48169b9e0b9af802f67e__section_tzl_3dm_ynb"/>

## Best Practice Guidelines

-   The quota assigned to you can be used in multiple subaccounts. The Custom Domain Manager counts only the activated certificates, and each activated certificate can have multiple Subject Alternative Names \(SANs\), with different statuses. As a result, even with just one quota, you can manage different custom domains.

-   Your total global quota accounts for the sum total of all the subaccounts or Cloud Foundry organizations that you own.

    > ### Example:  
    > If your global quota is 10 and you have three subaccounts, then your total global quota of 10 has to be distributed among the three subaccounts.

-   As soon as you activate a new certificate with the corresponding SAN\(s\), the old one is automatically deactivated and your quota remains the same as before.

**Related Information**  


[Configuring Custom Domains](../20-Configuration/configuring-custom-domains-1fbba52.md "To make sure that your domain is trusted by way of activated server certificates, and that all application data is protected, you must set up secure TLS/SSL communication. Then, make your application reachable via your custom domain and route traffic to it.")

[Manage Reserved and Custom Domains](../20-Configuration/manage-reserved-and-custom-domains-25ec7ea.md "To make your applications reachable and secure under your own domain, use the Custom Domain Manager to create and manage your reserved and custom domains. A reserved domain is a domain name that you can reserve inside a number of Cloud Foundry landscapes.")

[Manage Server Certificates](../20-Configuration/manage-server-certificates-1c4cbe6.md "Create a new server certificate and a certificate signing request (CSR) to obtain a certificate for your custom domains from a trusted certificate authority.")

