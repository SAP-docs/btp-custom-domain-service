<!-- loio1deab96e7aec447fbf8b683ba91a42e0 -->

# Initial Setup

This section provides information on the initial setup of the Custom Domain Manager in the Cloud Foundry environment.

To use the Custom Domain Manager, you have to complete some initial steps. Also, take a good look at the [Prerequisites](prerequisites-b791984.md) section.

1.  Make sure that the Custom Domain Manager is entitled to your subaccount; see [Managing Entitlements and Quotas Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/c8248745dde24afb91479361de336111.html "When you purchase an enterprise account, you are entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.") :arrow_upper_right: for more information.

2.  Subscribe to the Custom Domain Manager by using the SAP BTP cockpit in the *Instances and Subscriptions* tab of your subaccount.

    To subscribe to multitenant applications from the Subscriptions page in the SAP BTP cockpit, see [Subscribe to Multitenant Applications in the Cloud Foundry Environment Using the Cockpit](https://help.sap.com/products/BTP/65de2977205c403bbc107264b8eccf4b/7a3e39622be14413b2a4df7c02ca1170.html?version=Cloud).

3.  Choose *Create* to create a new instance or subscription.

4.  After you select *Custom Domain* as the *Service*, select *standard* as the *Plan*.

    > ### Caution:  
    > The *custom\_domains* plan is for the previous version of the Custom Domain service.

    > ### Note:  
    > There are no initial parameters for the service.

5.  Once you have subscribed, select *Go to Application* to open the Custom Domain Manager and log in there.

6.  Check the [Prerequisites](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Cloud/en-US/48cdbe7a64f3475586dc2f4d11c5603c.html "Before configuring custom domains, you have to make some preliminary steps and fulfill a number of prerequisites.") :arrow_upper_right: section; see the related link for more information.


