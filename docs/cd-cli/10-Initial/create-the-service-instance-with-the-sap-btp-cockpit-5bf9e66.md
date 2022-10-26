<!-- loio5bf9e66f8ec448849313057bf5786d83 -->

# Create the Service Instance with the SAP BTP Cockpit

To use the Custom Domain service for your applications, use the SAP BTP cockpit to create a service instance for your Cloud Foundry organization.



<a name="loio5bf9e66f8ec448849313057bf5786d83__prereq_zfk_v4v_cjb"/>

## Prerequisites

Configure the entitlement for the Custom Domain service and assign it to the subaccount that wants to use the service; see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html "Assign entitlements to subaccounts by adding service plans and distribute the quotas available in your global account to your subaccounts using the SAP BTP cockpit.") :arrow_upper_right:.



<a name="loio5bf9e66f8ec448849313057bf5786d83__context_csg_1l2_wgb"/>

## Context

If you want to use a service from SAP BTP, you have to first create a service instance for that service.

> ### Restriction:  
> Although creating a service instance with the SAP BTP cockpit is possible, further steps like configuring and managing custom domains are only available within the Cloud Foundry command-line interface.



## Procedure

1.  Log in to your SAP BTP cockpit.

2.  Choose your Global Account.

3.  Choose *Subaccounts*.

4.  Choose your Subaccount.

5.  Choose *Spaces*.

6.  Choose your Space.

7.  Choose *Services* \> *Service Marketplace*.

8.  Choose *Custom Domain*.

9.  Choose *Instances*.

10. Choose *New Instance*.

11. Choose a service plan from the dropdown list, and then choose *Next*.

    There is only one service plan \(custom\_domains\) available.

12. \(Optional\) Specify a JSON file or specify parameters in the JSON format, and then choose *Next*.

13. Enter a name for the service instance; for example, "custom-domain-service".

    > ### Note:  
    > Assigning a descriptive name helps you to distinguish it from your other service instances.

14. Choose *Finish*.




<a name="loio5bf9e66f8ec448849313057bf5786d83__result_ncz_w4x_vgb"/>

## Results

You have now created a service instance for custom domains.

> ### Note:  
> You have to create the service instance only once for every organization. You don't have to bind this service to an application.

**Related Information**  


[Using Services in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f22029f0e7404448ab65f71ff5b0804d.html "Learn more about using services in the Cloud Foundry environment, how to create (user-provided) service instances and bind them to applications, and how to create service keys.") :arrow_upper_right:

[Create Service Instances Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5516f912bae84922ba8c8eb46b8bfce5.html "") :arrow_upper_right:

[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

