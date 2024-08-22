<!-- loioe696d4548d3a40dbbf8b9868e8b4af53 -->

# Manage TLS Configurations

Create new TLS configurations that can be used for one or multiple server certificate activations.



## Procedure

Create your configurations.

1.  Choose the *TLS Configurations* tile.

2.  Choose *Add* to use the wizard to create each required configuration.

3.  Enter a name and choose *Next Step*.

    > ### Note:  
    > The *Client Authentication \(mTLS\)* mode is displayed as *disabled* by default.
    > 
    > Once the new configuration has been created, *Client Authentication \(mTLS\)* can be turned on by adding one or multiple trusted CA certificates.

4.  Choose *Next Step*.

5.  The summary information displays the entered configuration name and the status of the mTLS mode again. Choose *Finish* to exit the wizard and manage the created configuration.

    In the *Configuration* pane, under the *General Information* section, you can use the*Edit* button to change the name, if desired. You can also use the *Duplicate* button to copy the existing configuration, with a new name. Alternatively, you can delete it by using the *Delete* button and then create a new one again, if desired.

    > ### Restriction:  
    > Configurations that are already in use cannot be edited or deleted; they can only be duplicated.

6.  If you want to turn the *Client Authentication \(mTLS\)* mode on, from the corresponding drop-down list, select *optional* or *required*, as the case may be.

7.  Next, select the minimum and maximum protocol versions from their corresponding drop-down lists.

    The selected *Protocol Version \(min.\)* cannot be higher than the *Protocol Version \(max.\)*.

8.  You can also use the *Cipher Suite* drop-down list to select the cipher suite\(s\) that you want to use \(in any order\), according to the protocol version\(s\) that you have selected. If left blank, the default option will be used.

    > ### Restriction:  
    > For the 1.3 protocol version, you have to select the *\(1.3\) TLS\_AES\_128\_GCM\_SHA256 mandatory* option. This mandatory one can stand alone and be the only one you select. However, you cannot select a list of cipher suites without including the mandatory option.
    > 
    > If both your minimum and maximum protocol versions are 1.2, you cannot select cipher suites prefixed with \(1.3\), and similarly, if both versions are 1.3, you cannot select cipher suites prefixed with \(1.2\).

9.  \(Optional\) You can deselect the *Enable HTTP/2* check box to remove the use of the HTTP/2 protocol version.
10. Switch to the *Trust List* tab and choose *Add Trust List* to upload your list of trusted certificates and assign it to your custom domains.

    On adding the trust list, client authentication is enabled. However, when the last CA certificate is removed from the trust list, client authentication is automatically turned off.

11. Copy your trusted certificates list into the *Add PEM* text box and choose *Submit*.

    > ### Restriction:  
    > The number of trusted CA certificates per TLS configuration must not exceed 256 certificates.
    > 
    > The total size of all the trusted CA certificates per TLS configuration must not exceed 512 KB.




<a name="loioe696d4548d3a40dbbf8b9868e8b4af53__result_kbn_vhr_qpb"/>

## Results

The list of trusted certificates added are displayed and as long as they aren't in use yet, can be viewed again or deleted by using the *Show* or *Delete* icons, respectively. Certificates that are in use can only be viewed, not deleted.

**Default TLS Configurations**


<table>
<tr>
<th valign="top">

TLS Configurations

</th>
<th valign="top">

TLS Protocol Version

</th>
<th valign="top">

HTTP Protocol Version

</th>
</tr>
<tr>
<td valign="top">

Created with the Cloud Foundry CLI plugin for custom domains

</td>
<td valign="top">

1.2

</td>
<td valign="top">

HTTP/1.1

</td>
</tr>
<tr>
<td valign="top">

Created in the Custom Domain Manager

</td>
<td valign="top">

1.2, 1.3

</td>
<td valign="top">

HTTP/1.1, HTTP/2

</td>
</tr>
</table>

<a name="reference_jb3_ys1_3vb"/>

<!-- reference\_jb3\_ys1\_3vb -->

## Using Legacy TLS Configurations in Custom Domain Manager Activations

When working with the Cloud Foundry CLI plugin for custom domains, a default TLS configuration is created, which can also be seen in the Custom Domain Manager.



-   Default mTLS configurations that are created without a trust list are named *Default - Legacy*.

-   Default mTLS configurations that are created with a trust list are named *Default with Client Authentication - Legacy \#*. This \# \(number\) is a unique identifier.


If a legacy TLS configuration is used for a server certificate activation, it must be converted into a standard TLS configuration. The activation wizard will then ask you for a new name.

<a name="reference_ofm_vr2_sbc"/>

<!-- reference\_ofm\_vr2\_sbc -->

## Client Certificate Authentication \(Mutual TLS\)

Client certificate authentication, or mutual TLS \(mTLS\) can be optionally or mandatorily turned on for a custom domain.



In addition to the TLS configuration and the TLS handshake procedure that is performed by the BTP Cloud Foundry load balancer, your called application should consider additional hardening and client mapping procedures.

For more information, see SAP Note [3472521](https://me.sap.com/notes/3472521) \(Client Certificate Authentication \(mTLS\) in SAP BTP, Cloud Foundry Runtime\).

