<!-- loio7ad1e85b1cc54366b98c69164731a54d -->

# Manage SaaS Routes

Use the Custom Domain Manager to select your existing SaaS subscriptions and create custom routes for them, in addition to their standard routes.



<a name="loio7ad1e85b1cc54366b98c69164731a54d__prereq_sfy_vww_jjb"/>

## Prerequisites

-   Make sure that you’ve done the previous steps of the [Creating Custom Domains with TLS/SSL Server Authentication](https://help.sap.com/viewer/74af813c7ee2457cb5eddca0cc70a0c1/Dev/en-US/afeb1e77fc2f4365803049e9407449eb.html "Using custom domains with server authentication lets you establish secure communication between clients and your application.") :arrow_upper_right: process.

    > ### Note:  
    > For PaaS: Create and deploy an application within the Cloud Foundry environment. For more information on deploying an app, see the related link.
    > 
    > For SaaS: Subscribe to a SaaS application and write down the default URL of the SaaS application.

-   Be an administrator in your global account.

-   Be an administrator in the subaccount that has subscribed to the SaaS application.

-   Be a security administrator in the subaccount that has subscribed to the SaaS application.

-   Only for the Cloud Foundry environment: Be a space developer in the subaccount that has subscribed to the SaaS application.

    Please refer to the customer guide of your SaaS application to check if you must request an additional SaaS route configuration. In any case, the following steps must be performed.




<a name="loio7ad1e85b1cc54366b98c69164731a54d__steps_jxs_5fy_4pb"/>

## Procedure

1.  Map the application to your custom domain.

    1.  Choose the *SaaS Routes* tile.

    2.  Choose *Create Custom Route* to map a route to your application.

    3.  Select the tenant that you want to use.

        -   If you want to stay with the current subaccount that you are using, select the *Continue with current tenant ID* check box.

        -   If you want to use a different subaccount, deselecting this check box displays the *Tenant ID* text field, in which you can enter the ID of the desired subaccount.

    4.  Select the SaaS subscription for which you want to map the route and choose *Next Step*.

        For PaaS users, if you have created and deployed your application within the Cloud Foundry environment, you will see your subscription in the list of subscribed applications.

    5.  Optional. In the *Edit Route \(optional\)* step of the wizard, you can still edit the route you entered by making the necessary changes in the text field.

        > ### Tip:  
        > You can also use this text field to enter a completely new route; if for example, you have multiple subaccounts in the landscape or region.
        > 
        > If you encounter an error because your custom domain is missing from the `redirect-uris` parameter of the application's security descriptor file, refer to the following solution in the guided answers format.
        > 
        > -   [The redirect\_uri has an invalid domain](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2437/actions/32393:44353)

    6.  Select the desired custom domain from the list and choose *Next Step*.

    7.  If required, set a hostname and choose *Finish*. This field can be left empty too.

        > ### Example:  
        > myapp.applications.example.com


    Only the hostname and domain need to be mapped in a SaaS route; the rest of the standard URL remains as is and is forwarded to the called application.

    > ### Restriction:  
    > You can't map a route to a SaaS application for a domain that has only been shared with your organization. In this case, the mapping has to be done under the organization where the domain has been created.
    > 
    > Also, you can map routes across secondary subaccounts only if those subaccounts belong to the same global account. You cannot map the routes of a tenant that belongs to a different global account.




<a name="loio7ad1e85b1cc54366b98c69164731a54d__result_ajs_djy_4pb"/>

## Results

The custom routes are created and displayed in a list.

An active status for a route signifues that a certificate has been activated for the given domain. However, you can still delete that route and create a new one, if desired.

**Related Information**  


[Deploy Business Applications in the Cloud Foundry Environment](https://help.sap.com/viewer/6cdb9cff1d9b4877b9da90e5020a32d2/Internal/en-US/4946ea5421374924963ce8575a5f3d05.html "When an application for the Cloud Foundry environment resides in a folder on your local machine, you can deploy it and start it by executing the command line interface (CLI) command push. To deploy business applications bundled in a multitarget application archive, you have to use the command deploy-mta.") :arrow_upper_right:

