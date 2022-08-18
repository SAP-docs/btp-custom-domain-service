<!-- loio8ecabca8e9cc449f9de3eb34870ef490 -->

# Sharing Custom Domains

Use the Cloud Foundry command-line interface to share your custom domains across multiple Cloud Foundry organizations, to make them available for other users.



<a name="loio8ecabca8e9cc449f9de3eb34870ef490__prereq_e5y_lv3_vgb"/>

## Prerequisites

You must have either **Admin** rights or **Org Manager** rights for both your Cloud Foundry organization and the Cloud Foundry organization that you want to share your custom domain with.



## Context

When you create a domain with `cf create-domain`, the domain is private. If you want to make domains available to users in other Cloud Foundry organizations, you have to share them.

> ### Note:  
> When you share a custom domain, you also share its configuration; for example, certificate-based server or client authentication configuration. Although the configuration is shared, it can only be changed within the organization that it has been created in.



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Share the domain with another Cloud Foundry organization:

    ```
    cf share-private-domain <Other Cloud Foundry Org> <Custom Domain>
    ```

    > ### Sample Code:  
    > ```
    > cf share-private-domain otherOrg applications.example.com
    > ```

    > ### Note:  
    > In this case, `otherOrg` is a Cloud Foundry organization that you have **Org Manager** rights to. If you don't have the necessary permissions, you get an error message saying ***"FAILED Organization otherOrg not found"***.




<a name="loio8ecabca8e9cc449f9de3eb34870ef490__result_er1_vy3_vgb"/>

## Results

Users in the organization **otherOrg** are now able to map applications to the custom domain **applications.example.com**.

**Related Information**  


[Learn more about shared domains in the Cloud Foundry environment.](https://docs.cloudfoundry.org/devguide/deploy-apps/routes-domains.html#shared-domains)

[Learn more about roles and permissions in the Cloud Foundry environment](https://docs.cloudfoundry.org/concepts/roles.html#roles)

