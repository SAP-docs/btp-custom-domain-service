<!-- loio6da3c8d68b854d069a5e2d525af74067 -->

# Using a Custom Domain Accepted from Handover

You can set up and activate server certificates by using the custom domain in your extension landscape.



## Context

Once the *Target Subaccount* has accepted a domain handover, your custom domains, SaaS routes, and server certificates can make use of that domain. You can do this while your live applications and routes using the custom domain in your main landscape are still active. Use a local DNS or local machine host mapping, or use a browser or client that allows you to ignore any TLS errors that might be caused by wrong certificate host names.



## Procedure

1.  Log on to the *Target Subaccount* and open Custom Domain Manager.

2.  Choose the *Domains* tile.

    The custom domain is listed under the *Reserved Domains* tab and can be selected to create custom domains under the *Custom Domains* tab.

3.  Switch to the *SaaS Routes* tab.

    The custom domain can now be selected to create new SaaS routes.

4.  Now, switch to the *Server Certificates* tab.

    The custom domain can now be selected to create new server certificates.

    > ### Note:  
    > The new server certificates must be activated and all the Cloud Foundry routes must be created and tested.

5.  If all the tests are successful, change the public DNS CNAME from the main to the extension landscape.

6.  Perform all the tests again.


