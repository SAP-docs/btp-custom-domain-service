<!-- loio0ada62e09ee64d1ca1446b7853403b81 -->

# Organization not Found in Custom Domain Certificates Registry: You Have to Create an Instance of Service INFRA First



<a name="loio0ada62e09ee64d1ca1446b7853403b81__section_nph_dj4_hdc"/>

## Scenario

You tried to execute a command of the custom domain service and received the following error message:

```
Organization not found in Custom Domain Certificates registry: You have to create an instance of the INFRA service first.


```



<a name="loio0ada62e09ee64d1ca1446b7853403b81__section_oph_dj4_hdc"/>

## Reason

The reason for this error is that you tried to execute a command of the custom domain service without creating a service instance of the custom domain service first.



<a name="loio0ada62e09ee64d1ca1446b7853403b81__section_pph_dj4_hdc"/>

## Solution

Create a Service Instance of the Custom Domain Service



### Prerequisites

-   [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/4ef907afb1254e8286882a2bdef0edf4.html).

-   Configure the entitlement for the Custom Domain service and assign it to the subaccount that wants to use the service. See [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/5ba357b4fa1e4de4b9fcc4ae771609da.html).




### Create a service instance

1.  Log in to your Cloud Foundry Account.

    ```
    cf login
    ```

2.  Enter your credentials.
3.  Create the service instance.

    ```
    cf create-service INFRA custom_domains <custom-domain-service>
    ```

    ***INFRA*** is a fixed value for the service, ***custom\_domains*** is a fixed value for the service plan, and ***custom-domain-service*** is a name that you can choose for the service instance. Assigning it a descriptive name helps you to distinguish it from your other service instances.


For more information, see [Create the Service Instance with the Cloud Foundry CLI](https://help.sap.com/docs/CUSTOM_DOMAINS/74af813c7ee2457cb5eddca0cc70a0c1/8eef2cc907a24fbb999507f8ff15e096.html?version=Cloud).

