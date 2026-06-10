<!-- loio3d39403931e84a6191bef5e1fe4a8e75 -->

# Update Server Certificates

Updating an existing and activated server certificate requires a new private key. Regular cryptographic key rotation is a basic security policy in SAP BTP. Custom Domain Service follows this policy and you cannot turn it off. Therefore, you can replace the current server certificate; and without any downtime.



## Procedure

1.  In the *Server Identities* tile, choose *Add* to create a new server certificate CSR with the very same Common Name and Subject Alternative Names.

2.  Get a new certificate from the same or a different trust center CA.

3.  Upload the new certificate and its chain of CA certificates.

4.  Activate the new server certificate; select the same TLS configuration and SANs as the current one.




<a name="loio3d39403931e84a6191bef5e1fe4a8e75__result_dmt_hqn_4xb"/>

## Results

Such an activation automatically deactivates the current server certificate. In case of problems with the new one, you can still switch back and forth between the two server certificates of the server identity. However, once the new certificate should remain, the old one needs to be deleted to be prepared for the next replacement.



## Next Steps

Manual certificate lifecycle management is not recommended. Read more about [Automated Server Certificate Rotation](automated-server-certificate-rotation-5e983f4.md) by using the Custom Domain Manager REST API.

