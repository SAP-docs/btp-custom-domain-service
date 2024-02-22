<!-- loio338a39a5403a4293ac6096e2ffc8ffdf -->

# Custom Quota and License Calculation

**Custom Domains in DNS**



A custom domain is a customer-owned DNS zone or record that is applied to a standard SAP BTP URL. The recommended way to do this is to create a DNS CNAME in your own DNS, pointing to the SAP BTP landscape, API Fully Qualified Domain Name \(FQDN\).

> ### Example:  
> -   mysapbtpapp.customer.com. CNAME TO api.cf.eu10.hana.ondemand.com
> 
> -   mysapbtpapp.customer.com. CNAME TO api.cf.eu10-003.hana.ondemand.com

If multiple hosts and subdomains need to be included, a wildcard CNAME record can be used. A DNS wildcard includes all the subdomains and hostnames.

> ### Example:  
> \*.mysapbtpdomain.customer.com. CNAME TO api.cf.eu10.hana.ondemand.com



<a name="loio338a39a5403a4293ac6096e2ffc8ffdf__section_utk_3l1_rzb"/>

## Custom Domains in TLS

For each custom domain in SAP BTP Cloud Foundry, there must be a corresponding X.509 server certificate that lists the domain or hostname. Such Subject Alternative Names \(SANs\) can be a concrete host FQDN, or a wildcard domain.

While DNS CNAME wildcards are multilevel, a TLS certificate wildcard is only single level. However, one certificate can contain multiple SANs.

> ### Example:  
> ```
> mysapbtpdev.customer.com
> mysapbtptest.customer.com
> mysapbtpprod.customer.com
> ```
> 
> ```
> *.mysapbtpdomain.customer.com
> *.test.mysapbtpdomain.customer.com
> *.prod.mysapbtpdomain.customer.com
> ```

Of course, there are good reasons for having or not having several SANs in a single certificate.

For example, it is not recommended to combine development and testing purposes with productive ones because you cannot remove or replace such certificates independently.



<a name="loio338a39a5403a4293ac6096e2ffc8ffdf__section_yqg_sl1_rzb"/>

## Quota and Entitlements

Custom Domain Service requires one quota in your subaccount entitlement for each server certificate that is activated, independent of the included SANs.

Although you can activate single SANs in Custom Domain Manager, it is the server certificate holding the SAN that counts. This allows you to replace a server certificate without disruption, although you have only one quota in your entitlement. Also, this allows you to use one server certificate with multiple SANs and activated with different TLS configurations.



<a name="loio338a39a5403a4293ac6096e2ffc8ffdf__section_wth_5l1_rzb"/>

## License Calculation, Standard Case

The standard case is that each activated certificate \(with one or more activated SANs\) requires one quota and costs one license. The total number of activated server certificates is the number of licenses that you have to pay for.

> ### Example:  
> 
> <table>
> <tr>
> <th valign="top">
> 
> Region
> 
> </th>
> <th valign="top">
> 
> Landscape
> 
> </th>
> <th valign="top">
> 
> Server Certificates
> 
> </th>
> <th valign="top">
> 
> SANs
> 
> </th>
> <th valign="top">
> 
> Quota
> 
> </th>
> <th valign="top">
> 
> Licenses
> 
> </th>
> </tr>
> <tr>
> <td valign="top">
> 
> EU10
> 
> </td>
> <td valign="top">
> 
> eu10
> 
> </td>
> <td valign="top">
> 
> 1 activated
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> EU20
> 
> </td>
> <td valign="top">
> 
> eu20-001
> 
> </td>
> <td valign="top">
> 
> 2 activated
> 
> </td>
> <td valign="top">
> 
> 6
> 
> </td>
> <td valign="top">
> 
> 2
> 
> </td>
> <td valign="top">
> 
> 2
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> US20
> 
> </td>
> <td valign="top">
> 
> us20
> 
> </td>
> <td valign="top">
> 
> 3 activated
> 
> </td>
> <td valign="top">
> 
> 10
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> </tr>
> </table>



<a name="loio338a39a5403a4293ac6096e2ffc8ffdf__section_y4h_3m1_rzb"/>

## License Calculation, Extension Landscape Case

If your global account contains one or more subaccounts in the same region; for example, EU10; but you have activated server certificates in more than one associated landscape, then the landscape with the largest number of activations is used. Its total number of activations is the number of licenses that you have to pay for.

> ### Example:  
> ****
> 
> 
> <table>
> <tr>
> <th valign="top">
> 
> Region
> 
> </th>
> <th valign="top">
> 
> Landscape
> 
> </th>
> <th valign="top">
> 
> Server Certificates
> 
> </th>
> <th valign="top">
> 
> SANs
> 
> </th>
> <th valign="top">
> 
> Quota
> 
> </th>
> <th valign="top">
> 
> Licenses
> 
> </th>
> </tr>
> <tr>
> <th valign="top">
> 
> Region
> 
> </th>
> <th valign="top">
> 
> Landscape
> 
> </th>
> <th valign="top">
> 
> Server Certificates
> 
> </th>
> <th valign="top">
> 
> SANs
> 
> </th>
> <th valign="top">
> 
> Quota
> 
> </th>
> <th valign="top">
> 
> Licenses
> 
> </th>
> </tr>
> <tr>
> <th valign="top">
> 
> Region
> 
> </th>
> <th valign="top">
> 
> Landscape
> 
> </th>
> <th valign="top">
> 
> Server Certificates
> 
> </th>
> <th valign="top">
> 
> SANs
> 
> </th>
> <th valign="top">
> 
> Quota
> 
> </th>
> <th valign="top">
> 
> Licenses
> 
> </th>
> </tr>
> <tr>
> <td valign="top" rowspan="2">
> 
> EU10
> 
> </td>
> <td valign="top">
> 
> eu10
> 
> </td>
> <td valign="top">
> 
> 1 activated
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> eu10-003
> 
> </td>
> <td valign="top">
> 
> 1 activated
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 0
> 
> </td>
> </tr>
> <tr>
> <td valign="top" rowspan="2">
> 
> EU10
> 
> </td>
> <td valign="top">
> 
> eu10
> 
> </td>
> <td valign="top">
> 
> 3 activated
> 
> </td>
> <td valign="top">
> 
> 7
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> eu10-003
> 
> </td>
> <td valign="top">
> 
> 1 activated
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 1
> 
> </td>
> <td valign="top">
> 
> 0
> 
> </td>
> </tr>
> <tr>
> <td valign="top" rowspan="2">
> 
> EU10
> 
> </td>
> <td valign="top">
> 
> eu10
> 
> </td>
> <td valign="top">
> 
> 3 activated
> 
> </td>
> <td valign="top">
> 
> 7
> 
> </td>
> <td valign="top">
> 
> 3
> 
> </td>
> <td valign="top">
> 
> 0
> 
> </td>
> </tr>
> <tr>
> <td valign="top">
> 
> eu10-003
> 
> </td>
> <td valign="top">
> 
> 4 activated
> 
> </td>
> <td valign="top">
> 
> 4
> 
> </td>
> <td valign="top">
> 
> 4
> 
> </td>
> <td valign="top">
> 
> 4
> 
> </td>
> </tr>
> </table>

For more information about license reporting and billing, see SAP Note [3423355](https://me.sap.com/notes/3423355).

