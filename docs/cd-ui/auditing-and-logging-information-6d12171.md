<!-- loio6d121719db98496c9e34b116e2118ab6 -->

# Auditing and Logging Information

Here you can find a list of the security events that are logged by the Custom Domain service.

**Security events written in audit logs**


<table>
<tr>
<th valign="top">

Event grouping

</th>
<th valign="top">

What events are logged

</th>
<th valign="top">

How to identify related log events

</th>
<th valign="top">

Additional information

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Service-related events

</td>
<td valign="top">

Create a service instance

</td>
<td valign="top">

```
"attributes":[
        {
            \"name\":\"service instance Id\",
            \"old\":\"\",
            \"new\":\"<ServiceInstanceID>\"
        },
        {
            \"name\":\"organization Id\",
            \"old\":\"\",
            \"new\":\"<OrganizationID>\"
        },
        {
            \"name\":\"space Id\",
            \"old\":\"\",
            \"new\":\"<SpaceID>\"
        }
    ],
```

`\"success\":true,`

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Delete a service instance

</td>
<td valign="top">

***Deletion of data for *<tenant\>* started:***

***Service *<ID\>* with plan *<ID\>* is being deprovisioned***

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Instance-related events

</td>
<td valign="top">

Generate a new private and public key pair

</td>
<td valign="top">

***New Identity with alias *<KeyName\>* for domain *<name\>* created.***

```
 "attributes":[
       {
           \"name\":\"alias\",
           \"new\":\"<KeyName>\"},
           {
               \"name\":\"subject\",
               \"new\":\"CN=<Value>\"
           }
   ],
```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Delete a private key

</td>
<td valign="top">

***Identity with alias *<KeyName\>* for domain *<name\>* deleted\\***

</td>
<td valign="top">

Deleting the private key also deletes the public key.

</td>
</tr>
<tr>
<td valign="top">

Activate a server certificate for a set of domains

</td>
<td valign="top">

***Domain *<name\>* activated\\",\\"attributes\\***

```
"attributes":[
      {\"name\":\"Name\",
      \"new\":\"<Value>"},{\"name\":\"State\"},
      {\"name\":\"Trust\"}
    ],
    \"category\":\"audit.configuration\",
    \"tenant\":\"<TenantID>\",
    \"customDetails\":{}}"
```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Deactivate a certificate for a given domain

</td>
<td valign="top">

***Domain *<name\>* deactivated\\***

```
"attributes":[
        {
            \"name\":\"Trust\"
        },
        {
            \"name\":\"Name\",\"old\":\"<Value>"
        },
        {
            \"name\":\"State\",
            \"old\":\"in progress\"
        }
    ],
```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Enable client authentication for a domain

</td>
<td valign="top">

***Enabled client authetication for domain *<name\>*\\***

```
"attributes":[
        {
            \"new\":\"<Value>"
        },
        {
            \"name\":\"Trust\"
        }
    ],
```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Disable client authentication for a domain

</td>
<td valign="top">

***Disabled client authentication for domain *<name\>*.\\***

```
"attributes":[
        {
            \"name\":\"Trust\",
            \"old\":\"-----BEGIN CERTIFICATE-----\\...\\n-----END CERTIFICATE-----\\n\"
        }
    ],
```



</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Upload a certificate and CA chain for a given key

</td>
<td valign="top">

***Cetificate Chain for Identity *<value\>* and domain *<name\>* uploaded\\***

```
"attributes":[
        {
            \"name\":\"Chain\",
            \"new\":\"-----BEGIN CERTIFICATE-----\\...\\n-----END CERTIFICATE-----\\n\"
        }
    ],
```



</td>
<td valign="top">

 

</td>
</tr>
</table>



<a name="loio6d121719db98496c9e34b116e2118ab6__section_xwh_nwc_r2c"/>

## Sending Configuration Data to SAP Cloud ALM

To fulfill security requirements, Custom Domain Manager sends user configurations in a standardised format to SAP Cloud ALM. SAP Cloud ALM is an offering for application lifecycle management \(ALM\). It’s intended for customers who use solutions provided by SAP, and who do not want to use their own ALM on-premise platform to manage those solutions.

For more information, see [Configuration & Security Analysis - Content](https://support.sap.com/en/alm/sap-cloud-alm/operations/expert-portal/configuration-security-analysis/csa-content.html).

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

