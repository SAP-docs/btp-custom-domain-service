<!-- loioa6ee7f43b6d24a25a045cf01718b5c7c -->

# Repair TLS Configurations with Deprecated Cipher Suites

Deprecated cipher suites are not supported by HAProxy or accepted for the establishment of a connection. Therefore, your TLS configurations in Custom Domain Manager need to be updated.



## Context

1.  Choose the *TLS Configurations* tile.

    In the list of your TLS configurations, there is a *Deprecated Cipher* label, indicating any affected TLS configurations.

    -   If your TLS configuration is `in use`:

        1.  Select the TLS configuration in the list.

        2.  Create a duplicate of your TLS configuration.

            The deprecated cipher suites are automatically removed for the duplicate.

        3.  Adapt the cipher suites to your needs.

        4.  Use the new TLS configuration to activate the server certificates that are using the old configuration.

            For more information, refer to: [Best Practices for Configuration Changes](best-practices-for-configuration-changes-e252d26.md)


    -   If your TLS configuration is `unused`:

        1.  Select the TLS configuration in the list.

        2.  Choose the *Repair* button.

            The TLS configuration will be updated.

        3.  Adapt the cipher suites to your needs.

        4.  You can now use the new TLS configuration to activate a server certificate.




