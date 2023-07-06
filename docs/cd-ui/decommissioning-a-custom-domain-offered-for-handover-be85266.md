<!-- loiobe85266eefe54c718024824655e51497 -->

# Decommissioning a Custom Domain Offered for Handover

Once the handover is done, the *Source Subaccount* can decommission the custom domain.



## Context

You can remove the custom domain from the main landscape.

> ### Note:  
> Do not start this before the migration of the live applications and Cloud Foundry routes that are using the custom domain in your extension landscape, has been successfully completed and tested. Ensure too that the DNS CNAME points to the extension landscape.



## Procedure

1.  Log on to the *Source Subaccount* and open Custom Domain Manager.

2.  Choose the *Server Certificates* tile.

3.  Deactivate and delete any server certificate that uses the custom domain.

4.  Switch to the *SaaS Routes* tab.

5.  Delete any SaaS route that uses the custom domain.

6.  Switch to the *Domains* tab.

7.  Under the *Custom Domains* tab, delete any corresponding custom domain listed.

8.  Under the *Reserved Domains* tab, delete any reserved domain using the custom domain.




<a name="loiobe85266eefe54c718024824655e51497__result_f3c_jcm_4xb"/>

## Results

Now the custom domain disappears from the *Domain Handover* tab in both the source and target subaccounts.

