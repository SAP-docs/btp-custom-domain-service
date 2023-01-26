<!-- loio25ec7eaf439341e7bf52a280d3797c6e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Reserved and Custom Domains

To make your applications reachable and secure under your own domain, use the Custom Domain Manager to create and manage your reserved and custom domains. A reserved domain is a domain name that you can reserve inside a number of Cloud Foundry landscapes.



<a name="loio25ec7eaf439341e7bf52a280d3797c6e__prereq_okg_lm2_tpb"/>

## Prerequisites

Domain reservations are linked to a global account and shared with all of its related subaccounts in the same region.

Although these domains are not listed other than in the subaccounts in which they were reserved, you can reserve and create subdomains in those accounts.

> ### Example:  
> In subaccount 1, the example.com super domain is reserved and you create a custom domain, sub1.example.com. Then, in subaccount 2, you can reserve and create the sub2.customer.com custom domain.

> ### Remember:  
> Domain reservations must be done in each landscape \(including its extensions\). A global custom domain reservation is not possible.

> ### Note:  
> Domain names are owned by the customer, not by SAP BTP. Therefore, you have to buy domain names from a registrar who sells domain names. Refer to [Prerequisites](../10-Initial/prerequisites-b791984.md) for more information.



## Procedure

1.  Log on to the Custom Domain Manager by entering your credentials.

2.  Create your custom domains:

    1.  Choose the *Domains* tile.

    2.  Choose *Add Reserved Domain* to add a domain name that you want to reserve for this and associated extension landscapes.

    3.  Enter the domain name and choose *Add*. It is now displayed in the list of *Reserved Domains*.

        You can create multiple reserved domains.

        > ### Example:  
        > example.com

    4.  Switch to the *Custom Domains* tab.


    -   If you're a PaaS customer with your own Cloud Foundry organization, choose *Create Custom Domain* and select *for your Subaccount's CF Organization*. The wizard first displays the landscape or region corresponding to your Cloud Foundry organization.
        1.  Choose *Next Step*.

        2.  Select the desired domain from the list of reserved domains and choose *Next Step*.

            You can select either the shared standard domain of your PaaS landscape or one of the top-level domains that you have reserved for the region.

        3.  Enter a subdomain name to be created as your custom domain and choose *Finish*.

            > ### Restriction:  
            > This is mandatory for the shared standard domain.

            > ### Example:  
            > applications.example.com

            Alternatively, leave the text field empty to use your own reserved domain as the custom domain.


    -   If you're a SaaS customer who subscribes to a Saas application, choose *Create Custom Domain* and select *for your Subaccount's SaaS Subscription*. The wizard first displays your subscribed applications, in their corresponding landscapes.
        1.  Select the desired SaaS application and choose *Next Step*.

        2.  Select the desired domain from the list of reserved domains and choose *Next Step*.

        3.  Enter a subdomain name and choose *Finish*.

            > ### Restriction:  
            > This is mandatory for the shared standard domain.

            > ### Example:  
            > applications.example.com

            Alternatively, leave the text field empty to use your own reserved domain as the custom domain.






<a name="loio25ec7eaf439341e7bf52a280d3797c6e__result_kxw_bqs_4pb"/>

## Results

The custom domains are created and displayed in a list, along with their corresponding landscape and status.

To delete unused reserved and custom domains, choose :wastebasket:\(Delete\).

> ### Note:  
> If you use the Cloud Foundry CLI to create your custom domains, you can choose the *Cloud Foundry Sync* button to synchronize the custom domains created in the CLI and list them in the UI. For more information about using the Custom Domain service for your applications by using the Cloud Foundry CLI to create a service instance for your Cloud Foundry organization, see the related link.

**Related Information**  


[What Is Custom Domain](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/4414cc43db2d4229b27b232a5590e253.html "Configure and expose your application under your own domain.") :arrow_upper_right:

