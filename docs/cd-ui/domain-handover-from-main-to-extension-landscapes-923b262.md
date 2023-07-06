<!-- loio923b26242996448cbf13bfddf1e82213 -->

# Domain Handover from Main to Extension Landscapes

You can use a reserved domain in an an extension landscape, instead of in the main one, where it was originally created.



## Context

> ### Example:  
> You have deployed Cloud Foundry applications in your Cloud Foundry environment in one of your BTP subaccounts, which is in a main landscape. Another subaccount has its environment in an extension landscape. To reduce complexity, you want to move your existing applications from the main to the extension landscape.

The *Domain Handover* wizard allows the handing over of the reservation and further control of a custom domain from a main to an extension landscape.

> ### Note:  
> Both subaccounts must belong to the same region and be in the same global account.
> 
> A domain handover cannot copy or move any existing custom domain server certificates across Cloud Foundry landscapes.

> ### Example:  
> You have a subaccount in the Cloud Foundry environment in the main landscape and a reserved \(and used\) custom domain, called *Source Subaccount*. You have another subaccount in the Cloud Foundry environment in an extension landscape, called *Target Subaccount*.



## Procedure

1.  [In the *Source Subaccount*, you can **offer** a custom domain to the *Target Subaccount*.](offer-a-custom-domain-for-handover-f17f788.md)

2.  [In the *Source Subaccount*, you can **revoke** an offered custom domain as long as it hasn't been accepted by the *Target Subaccount*.](revoke-a-custom-domain-handover-offering-ce9a195.md)

3.  [In your *Target Subaccount*, you can **accept** a custom domain that is **offered** for handover.](accept-a-custom-domain-handover-offering-9eb0d29.md)

4.  [Once the *Target Subaccount* accepts the domain handover, custom Domains, SaaS routes, and server certificates can make use of that subaccount.](using-a-custom-domain-accepted-from-handover-6da3c8d.md)

5.  [Once the handover is done, the *Source Subaccount* can decommission the custom domain.](decommissioning-a-custom-domain-offered-for-handover-be85266.md)

6.  The final step is to change the public DNS CNAME from the main to the extension landscape.


