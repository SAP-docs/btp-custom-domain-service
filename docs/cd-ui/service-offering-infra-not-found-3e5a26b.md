<!-- loio3e5a26b2dca3411aa74e6becd2bd17ce -->

# Service Offering INFRA not Found



<a name="loio3e5a26b2dca3411aa74e6becd2bd17ce__section_qd5_n4p_fdc"/>

## Scenario

You tried to create a service instance but get the following error message:

```
Service offering INFRA not found


```



<a name="loio3e5a26b2dca3411aa74e6becd2bd17ce__section_zry_n4p_fdc"/>

## Reason

The reason for this error is that the custom domain service has not been entitled to the subaccount that you are using to create the service instance.



<a name="loio3e5a26b2dca3411aa74e6becd2bd17ce__section_trt_q4p_fdc"/>

## Solution



### Entitle the custom domain service to your subaccount

1.  Navigate to your global account.
2.  From the navigation panel, choose **Entitlements** **\>** **Subaccount** **Assignments**.
3.  At the top of the page, select all the subaccounts for which you would like to configure or display entitlements.
4.  Choose **Go** to apply the filter.

    You will get a table for each of the subaccounts you selected, displaying the current entitlement and quota assignments.

5.  Choose **Configure Entitlements** to start editing entitlements for a particular subaccount.

    You can now edit the entitlements table.

6.  Add units for the **Custom Domain Certificates**service \(one unit equals one activated certificate\).
7.  When you're done, choose **Save** to save the changes and exit edit mode for that subaccount.

For more information about entitlements, see [Managing Entitlements and Quotas Using the Cockpit](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/c8248745dde24afb91479361de336111.html).

If the service that you want to entitle to a subaccount is not available in your global account, talk to your SAP sales contact person. **Note:** The Cloud Foundry and Neo environments have different quotas and entitlements, so make sure that you buy the quota or entitlement for the right environment, in this case Cloud Foundry.

