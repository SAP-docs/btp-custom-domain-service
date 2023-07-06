<!-- loio3d39403931e84a6191bef5e1fe4a8e75 -->

# Update Server Certificates

Updating an existing and activated server certificate requires a new private key. Regular cryptographic key rotation is a basic security policy in SAP BTP. Custom Domain Service follows this policy and you cannot turn it off. Therefore, you can replace the current server certificate; and without any downtime.



## Procedure

1.  Create a new server certificate CSR with the very same Common Name and Subject Alternative Names.

2.  Get a new certificate from the same or a different trust center CA.

3.  Upload the new certificate and its chain of CA certificates.

4.  Activate the new server certificate; select the same TLS configuration and SANs as the current one.




<a name="loio3d39403931e84a6191bef5e1fe4a8e75__result_dmt_hqn_4xb"/>

## Results

Such an activation will automatically deactivate the current server certificate.

