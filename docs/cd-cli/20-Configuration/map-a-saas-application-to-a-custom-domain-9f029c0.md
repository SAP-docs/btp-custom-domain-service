<!-- loio9f029c0ba0ab496fa2767b607eae924f -->

# Map a SaaS Application to a Custom Domain

To make your SaaS application reachable from a custom domain, use the custom domain CLI plugin.



<a name="loio9f029c0ba0ab496fa2767b607eae924f__prereq_sfy_vww_jjb"/>

## Prerequisites

-   Make sure that you’ve done the previous steps of the [Creating Custom Domains with TLS/SSL Server Authentication](creating-custom-domains-with-tls-ssl-server-authentication-afeb1e7.md) process.

-   Subscribe to a SaaS application and write down the default URL of the SaaS application.

-   Be an administrator in your global account.

-   Be an administrator in the subaccount that subscribed to the SaaS application.

-   Be a security administrator in the subaccount that subscribed to the SaaS application.

-   Be a space developer in the subaccount that subscribed to the SaaS application.


> ### Note:  
> Please refer to the customer guide of your SaaS application to check if you must request an additional SaaS route configuration. In any case, the following steps must be performed.



## Procedure

1.  Map the SaaS application to your custom domain.

    ```
    cf custom-domain-map-route <Default SaaS URL> <Application Hostname>.<Custom Domain>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-map-route trial321.enterprise-messaging.cfapps.eu10.hana.ondemand.com messaging.applications.example.com>
    > ```

    > ### Note:  
    > -   It can take until the next day to activate the route. The timezone depends on the region of your Cloud Foundry environment.
    > 
    > -   The default SaaS URL in this example consists of the following elements:`<subaccount-name>.<saas-app-name>.cfapps.<region>.hana.ondemand.com`.

    > ### Restriction:  
    > You can't map a route to a SaaS application for a domain that has only been shared with your organization. In this case, the mapping has to be done under the organization where the domain has been created.
    > 
    > Also, you can map routes across secondary subaccounts only if those subaccounts belong to the same global account. You cannot map the routes of a tenant that belongs to a different global account.

2.  Verify that the route has been created.

    ```
    cf custom-domain-routes
    ```


