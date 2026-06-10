<!-- loio8eef342cdfd3400f8d83c834ea2ed7a6 -->

# Sharing Reserved Domains

You can share a reserved domain with another SAP BTP subaccount by using an Access Control List \(ACL\).



## Context

> ### Example:  
> You have deployed Cloud Foundry applications in your Cloud Foundry environment in one of your BTP subaccounts. Another subaccount in the same region needs to use the same reserved domain, but for a different subdomain.

> ### Note:  
> -   Both subaccounts must belong to the same region, but may be in different global accounts.
> 
> -   Domain sharing cannot share, copy, or move any existing custom domain server certificates.
> 
> -   The target subaccount must also be subscribed to Custom Domain Manager.

> ### Example:  
> You have a subaccount and a reserved domain, called *Source Subaccount*. You have another subaccount, called *Target Subaccount*. It doesn't matter if one or both subaccounts use the Cloud Foundry environment or not.



## Procedure

1.  In the *Source Subaccount*, select the reserved domain and open its details.

2.  Choose *Add* to create a new ACL.

3.  In the *Add ACL Entry to Reserved Domain* pane, keep your global account ID, or enter the global account ID of the *Target Subaccount*, if it's different.

4.  Enter the subaccount ID for the *Target Subaccount*.

    > ### Tip:  
    > The scope is always *Domain*.

5.  Choose *Add* to create the new ACL.

    The reserved domain is listed as a new ACL entry, but with the status, *not used*.

6.  In the *Target Subaccount*, choose the *Reserved Domains* tab to open it.

7.  Create a new reserved domain with the same name.

    The details now list an ACL record for the reserved domain, with the status *used*.

    Both subaccounts can now use or delete the shared reserved domain.

    Both subaccounts can create custom domains based on this reserved domain, but as per the CF landscape, any custom domain must be unique.

    If one of the subaccounts deletes the reserved domain, the other subaccount is the only remaining owner.

    > ### Note:  
    > A handover of a custom domain from a CF main landscape to a CF extension landscape is still possible. However, reserved domain sharing ACLs allow many more scenarios than just that. It's important to start with a proper domain concept that allows maximal flexibility and avoids technical blockers.


