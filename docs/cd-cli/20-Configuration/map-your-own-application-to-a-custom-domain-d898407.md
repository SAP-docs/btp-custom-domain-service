<!-- loiod898407897f6466385959e364ce5018e -->

# Map Your Own Application to a Custom Domain

To make your application reachable from your custom domain, use the Cloud Foundry CLI to map a route to your application.



<a name="loiod898407897f6466385959e364ce5018e__prereq_ztr_14p_jgb"/>

## Prerequisites

Create and deploy an app within the Cloud Foundry environment. For more Information on deploying an app, see the related links.



## Procedure

1.  Map your application to your custom domain:

    ```
    cf map-route <Application Name> <Custom Domain> --hostname <Application Hostname>
    ```

    > ### Sample Code:  
    > ```
    > cf map-route app applications.example.com --hostname myapp
    > ```

    > ### Note:  
    > -   If you’ve already deployed your application, you probably specified a host name for it, either in the manifest file or while pushing the app. By default, the name of the app serves as its hostname; however, you can change it using the command `map-route`.
    > 
    > -   For more information about mapping and routes in the Cloud Foundry environment, visit: [https://docs.cloudfoundry.org/devguide/deploy-apps/routes-domains.html](https://docs.cloudfoundry.org/devguide/deploy-apps/routes-domains.html) 

    This command results in a route that looks like this: **https://myapp.applications.example.com**.

2.  Verify that the routing of your application is correct:

    ```
    cf routes
    ```


**Related Information**  


[Deploy Business Applications in the Cloud Foundry Environment](https://help.sap.com/viewer/6cdb9cff1d9b4877b9da90e5020a32d2/Internal/en-US/4946ea5421374924963ce8575a5f3d05.html "When an application for the Cloud Foundry environment resides in a folder on your local machine, you can deploy it and start it by executing the command line interface (CLI) command push. To deploy business applications bundled in a multitarget application archive, you have to use the command deploy-mta.") :arrow_upper_right:

