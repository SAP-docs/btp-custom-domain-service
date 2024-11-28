<!-- loiocb953575d1504551ae933a1f3e844d6e -->

# Quota Limit for Specified Service Plan has Exceeded



<a name="loiocb953575d1504551ae933a1f3e844d6e__section_or3_pj4_hdc"/>

## Scenario

You tried to activate a certificate and get the following error message:

```
Quota limit for specified service plan has exceeded: Please contact service administrator



```



<a name="loiocb953575d1504551ae933a1f3e844d6e__section_pr3_pj4_hdc"/>

## Reason

Your subaccount does not have enough quota to activate another certificate. One activated certificate equals one custom domain quota.



<a name="loiocb953575d1504551ae933a1f3e844d6e__section_ipm_qsp_fdc"/>

## Solution



### Assign More Quota to Your Subaccount

The solution consists of two steps. First you need to entitle more quota to the subaccount with the global account then you need to assign this quota to your Custom Domain service in your subaccount.



### Assign more custom domain quota to your subaccount with the global account

1.  Navigate to your global account.
2.  In the navigation panel, choose **Entitlements \> Subaccount Assignments**.
3.  At the top of the page, select all of the subaccounts for which you would like to configure or display entitlements.
4.  Choose **Go** to apply the filter.

    You will get a table for each of the subaccounts that you selected, displaying the current entitlement and quota assignments.

5.  Choose **Configure Entitlements** to start editing entitlements for a particular subaccount.

    You can now edit the entitlements table.

6.  Edit the quota for one or more service plans by using the plus or minus icon.
7.  When you're done, choose **Save** to save the changes and exit edit mode for that subaccount.



### Assign the new quota to your custom domain service

1.  Go to your subaccount.
2.  Choose **Entitlements**.
3.  Choose **Configure Entitlements**.
4.  Add more quota to the Custom Domain service using the plus icon.
5.  Choose **Save**.

