<!-- loio8987a2dfc5694b11876726f65daa0e06 -->

# Monitoring and Troubleshooting

This section provides information on troubleshooting-related activities for the Custom Domain service in the Cloud Foundry environment.



<a name="loio8987a2dfc5694b11876726f65daa0e06__section_uz5_5yv_vjb"/>

## Getting Support

If you encounter an issue with this service, we recommend that you follow the procedure below:



### Check Platform Status

Check the availability of the platform at [SAP Trust Center](https://www.sap.com/about/trust-center/cloud-service-status.html).

To get notifications for updates and downtimes, subscribe at the [Cloud System Notification Subscriptions](https://support.sap.com/en/my-support/systems-installations/cac.html) application. Create a subscription by specifying Cloud Product, Cloud Service, and Notification Type. For more information, see [Cloud System Notification Subscriptions User Guide](https://support.sap.com/content/dam/support/en_us/library/ssp/my-support/systems-installations/cac/csns_user_guide.pdf).

For more information about selected platform incidents, see [Root Cause Analysis](https://help.sap.com/viewer/product/SCP_RCA/Latest/en-US).



### Check Solutions

Use the solutions listed under this topic to find information about how to resolve issues that might occur when using the Custom Domain Service. Be aware that some processes during the creation of a custom domain can take until the next day; for example, activating an uploaded certificate or enabling client authentication. Make sure that you've waited the appropriate amount of time before investigating or creating a ticket.

We also recommend that you regularly check the SAP Notes and Knowledge Base for component `BC-CP-CF-SEC-DOM` in the [SAP Support Portal](https://support.sap.com/en/index.html). These contain information about program corrections and provide additional information.

If you encounter an error because your custom domain is missing from the `redirect-uris` parameter of the application's security descriptor file, refer to the following solution.

-   [The redirect_uri has an invalid domain](https://help.sap.com/viewer/6f35a23466ee4df0b19085c9c52f9c29/Cloud/en-US/e09b325cad9b4c65ac96cda71c775543.html "") :arrow_upper_right:




### Copy Support Information

When reporting an incident or error, it helps to have all the required information such as the global account ID, subaccount ID, subdomain, and any other important details handy.

1.  After logging on to the Custom Domain Manager by entering your credentials, on the *Home* screen, click your name on the top-right corner to select *User Information*.

    The popup window displayed contains all the required information.

2.  Click *Copy Support Information* to copy the details to the clipboard.

    You can now paste the information where desired.

    > ### Note:  
    > For data privacy reasons, the user details are not copied.




### Contact SAP Support

You can report an incident or error through the SAP Support Portal. For more information, see [Getting Support](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5dd739823b824b539eee47b7860a00be.html).

Please use the following component for your incident:


<table>
<tr>
<th valign="top">

Component Name

</th>
<th valign="top">

Component Description

</th>
</tr>
<tr>
<td valign="top">

`BC-CP-CF-SEC-DOM` 

</td>
<td valign="top">

Custom Domain Service \(in the Cloud Foundry environment\)

</td>
</tr>
</table>

When submitting the incident, we recommend including the following information:

-   Landscape information \(such as EU10, US10\)

-   The URL of the page where the incident or error occurs

-   The steps or clicks used to replicate the error

-   Screenshots, videos, or the text entered


**Related Information**  


[Getting Support](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Validation/en-US/5dd739823b824b539eee47b7860a00be.html "To get assistance, use the available support channels provided by SAP for Me.") :arrow_upper_right:

