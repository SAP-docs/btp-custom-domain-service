<!-- loioe696d4548d3a40dbbf8b9868e8b4af53 -->

# Manage TLS Configurations

Create new TLS configurations that can be used for one or multiple server certificate activations.



## Procedure

1.  Create your configurations.

    1.  Choose the *TLS Configurations* tile.

    2.  Choose *Add* to use the wizard to create each required configuration.

    3.  Enter a name and choose *Next Step*.

        > ### Note:  
        > The *Client Authentication \(mTLS\)* mode is displayed as *disabled* by default.
        > 
        > Once the new configuration has been created, *Client Authentication \(mTLS\)* can be turned on by adding one or multiple trusted CA certificates.

    4.  Choose *Next Step*.

    5.  The summary information displays the entered configuration name and the status of the mTLS mode again. Choose *Finish* to exit the wizard and manage the created configuration.

        In the *Configuration* pane, under the *General Information* section, you can use the*Edit* button to change the name, if desired. You can also use the *Clone* button to copy the existing configuration, with a new name. Alternatively, you can delete it by using the *Delete* button and then create a new one again, if desired.

        > ### Restriction:  
        > Configurations that are already in use cannot be edited or deleted; they can only be cloned.

    6.  If you want to turn the *Client Authentication \(mTLS\)* mode on, from the corresponding drop-down list, select *optional* or *required*, as the case may be.

    7.  Next, select the minimum and maximum protocol versions from their corresponding drop-down lists.

        The selected *Protocol Version \(min.\)* cannot be higher than the *Protocol Version \(max.\)*.

    8.  You can also use the *Cipher Suite* drop-down list to select the cipher suite\(s\) that you want to use \(in any order\), according to the protocol version\(s\) that you have selected. If left blank, the default option will be used.

        > ### Restriction:  
        > For the 1.3 protocol version, you have to select the *\(1.3\) TLS\_AES\_128\_GCM\_SHA256 mandatory* option. This mandatory one can stand alone and be the only one you select. However, you cannot select a list of cipher suites without including the mandatory option.
        > 
        > If both your minimum and maximum protocol versions are 1.2, you cannot select cipher suites prefixed with \(1.3\), and similarly, if both versions are 1.3, you cannot select cipher suites prefixed with \(1.2\).

    9.  \(Optional\) You can select the *Enable HTTP/2* check box to support the use of the HTTP/2 protocol version.
    10. Switch to the *Trust List* tab and choose *Add Trust List* to upload your list of trusted certificates and assign it to your custom domains.

        On adding the trust list, client authentication is enabled. However, when the last CA certificate is removed from the trust list, client authentication is automatically turned off.

    11. Copy your trusted certificates list into the *Add PEM* text box and choose *Submit*.




<a name="loioe696d4548d3a40dbbf8b9868e8b4af53__result_kbn_vhr_qpb"/>

## Results

The list of trusted certificates added are displayed and as long as they aren't in use yet, can be viewed again or deleted by using the *Show* or *Delete* icons, respectively. Certificates that are in use can only be viewed, not deleted.

