<!-- loio8eef2cc907a24fbb999507f8ff15e096 -->

# Create the Service Instance with the Cloud Foundry CLI

To use the Custom Domain service for your applications, use the Cloud Foundry CLI to create a service instance for your Cloud Foundry organization.



<a name="loio8eef2cc907a24fbb999507f8ff15e096__prereq_tvn_pm2_wgb"/>

## Prerequisites

-   Download and install the Cloud Foundry command-line interface \(CLI\); see [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/4ef907afb1254e8286882a2bdef0edf4.html "Download and set up the Cloud Foundry Command Line Interface (cf CLI) to start working with the Cloud Foundry environment.") :arrow_upper_right:.

-   Configure the entitlement for the Custom Domain service and assign it to the subaccount that wants to use the service; see [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html "Assign entitlements to subaccounts by adding service plans and distribute the quotas available in your global account to your subaccounts using the SAP BTP cockpit.") :arrow_upper_right:.




<a name="loio8eef2cc907a24fbb999507f8ff15e096__context_avy_1jg_zgb"/>

## Context

If you want to use a service from SAP BTP, you have to first create a service instance for that service.



<a name="loio8eef2cc907a24fbb999507f8ff15e096__steps_h2c_hkx_vgb"/>

## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Create the service instance:

    ```
    cf create-service INFRA custom_domains <Service Instance Name>
    ```

    > ### Sample Code:  
    > ```
    > cf create-service INFRA custom_domains custom-domain-service
    > ```

    > ### Note:  
    > `INFRA` is a fixed value for the Custom Domain service, `custom_domains` is a fixed value for the service plan, and `custom-domain-service` is an individual name that you can choose for the service instance. Assigning it a descriptive name helps you to distinguish it from your other service instances.




<a name="loio8eef2cc907a24fbb999507f8ff15e096__result_ncz_w4x_vgb"/>

## Results

You’ve now created a service instance for custom domains.

> ### Note:  
> You have to create the service instance only once for every organization. You don't have to bind this service to an application.

**Related Information**  


[Using Services in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/f22029f0e7404448ab65f71ff5b0804d.html "Learn more about using services in the Cloud Foundry environment, how to create (user-provided) service instances and bind them to applications, and how to create service keys.") :arrow_upper_right:

[Create Service Instances Using the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/a872531845d6416b8fa07a8b84875d7e.html "You can use the Cloud Foundry Command Line Interface (cf CLI) to create service instances.") :arrow_upper_right:

[Remove the Custom Domain Service Instance](../remove-the-custom-domain-service-instance-8f84532.md "Use the Cloud Foundry command-line interface to remove the custom domain service instance from your Cloud Foundry organization.")

