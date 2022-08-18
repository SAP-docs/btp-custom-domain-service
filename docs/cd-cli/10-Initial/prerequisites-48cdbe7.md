<!-- loio48cdbe7a64f3475586dc2f4d11c5603c -->

# Prerequisites

Before configuring custom domains, you have to make some preliminary steps and fulfill a number of prerequisites.



<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_e12_jfb_mgb"/>

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



<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_f12_jfb_mgb"/>

## Choose a TLS/SSL Certificate

To make sure that your domain is trusted and all your application data is protected, you have to get an appropriate TLS/SSL certificate from a Certificate Authority \(CA\). Determine the domains you want to be protected by this certificate. One certificate can be valid for a number of domains and subdomains but you can also use a dedicated certificate for each domain.

-   **Standard certificate** - A standard certificate protects one domain, for example. **www.example.com**.

-   **Wildcard certificate** - A wildcard certificate secures multiple applications of a domain, for example, **\*.example.com** covers any application under the domain **example.com**, like **myapp.example.com**, but not the domain **example.com** itself.

    This also works with subdomains, for example **\*.applications.example.com** covers any application under the subdomain **applications.example.com**, like **myapp.applications.example.com**, but not the subdomain **applications.example.com** itself.




<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_swb_b1v_lhb"/>

## Certificate Life Cycle Management

To make sure, that a secure connection to your applications is maintained, use a certificate life cycle management tool to monitor your certificates. You won't receive a warning from SAP BTP or the Custom Domain service if one of your certificates is about to expire.



<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_hrg_qvc_ygb"/>

## Ensure That You Have the Necessary Authorizations Within Your Cloud Foundry Account

To use the Cloud Foundry CLI to manage private domains within your Cloud Foundry organization, you need to have **Org Manager** rights.

To create a service instance of the Custom Domain service, and to use the Custom Domain CLI to manage the keys and certificates for your domains, you must also have the **Space Developer** role in the same space.

> ### Tip:  
> For an overview of roles and permissions in the Cloud Foundry environment, visit: [https://docs.cloudfoundry.org/concepts/roles.html\#roles](https://docs.cloudfoundry.org/concepts/roles.html#roles).



<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_of5_rqf_scb"/>

## Create a Service Instance

To use custom domains, you have to create a service instance for the Custom Domain service. To do so, you can either use the Cloud Foundry command-line interface or the SAP BTP Cockpit.

-   [Create the Service Instance with the Cloud Foundry CLI](create-the-service-instance-with-the-cloud-foundry-cli-8eef2cc.md)

-   [Create the Service Instance with the SAP BTP Cockpit](create-the-service-instance-with-the-sap-btp-cockpit-5bf9e66.md)




<a name="loio48cdbe7a64f3475586dc2f4d11c5603c__section_tzl_3dm_ynb"/>

## Best Practice Guidelines

Create a new separate space; for example, **custom-domains**, in the Cloud Foundry organization where all the custom domain-related management operations are done.

-   In this space, assign the **Space Developer** role to all the users allowed to manage custom domains.

-   Create only one service instance of the Custom Domain service in this space.

-   Create, manage, and share your custom domains from within the Cloud Foundry organization that contains the **custom-domains** space.

-   Use the Custom Domain CLI to manage the keys and certificates for your custom domains.


**Related Information**  


[Using Services in the Cloud Foundry Environment](https://help.sap.com/viewer/6cdb9cff1d9b4877b9da90e5020a32d2/Internal/en-US/f22029f0e7404448ab65f71ff5b0804d.html "Developers can bind applications running on SAP BTP with services offered by SAP and other services. Learn more about using services in the Cloud Foundry environment, how to create (user-provided) service instances and bind them to applications, and how to create service keys.") :arrow_upper_right:

[Creating Service Instances](https://help.sap.com/viewer/6cdb9cff1d9b4877b9da90e5020a32d2/Internal/en-US/8221b7434d8e484fab5ec5d219b7bf64.html "Use the SAP BTP cockpit or the Cloud Foundry Command Line Interface to create service instances:") :arrow_upper_right:

[Roles and Permissions in the Cloud Foundry Environment](https://docs.cloudfoundry.org/concepts/roles.html#roles)

