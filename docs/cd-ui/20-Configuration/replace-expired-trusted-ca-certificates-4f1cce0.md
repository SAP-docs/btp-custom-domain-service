<!-- loio4f1cce03099b42bd900548d2403ab988 -->

# Replace Expired Trusted CA Certificates

TLS configurations can have trusted CA certificates, which eventually expire. To prevent TLS connection issues, these trusted CA certificates need to be replaced in a timely manner.



<a name="loio4f1cce03099b42bd900548d2403ab988__context_rj1_wf1_fzb"/>

## Context

1.  Choose the *TLS Configurations* tile.

    In the list of your TLS configurations, the *Trust Lifetime* column displays the lowest lifetime left among the trusted CA certificates.

    -   If your TLS configuration is `in use`:

        1.  Select the TLS configuration in the list.

        2.  Create a duplicate of your TLS configuration.

        3.  Go to the *Trust List* tab.

        4.  Add the new trusted CA certificate to the trust list.

        5.  Make sure that the expiring or expired trust certificates are no longer needed.

            -   If they are no longer required, delete them from the trust list.


        6.  Use the new TLS configuration to activate the server certificates that are using the old configuration.

            For more information, refer to: [Best Practices for Configuration Changes](best-practices-for-configuration-changes-e252d26.md)


    -   If your TLS configuration is `unused`:

        1.  Select the TLS configuration in the list.

        2.  Go to the *Trust List* tab.

        3.  Add the new trusted CA certificate to the trust list.

        4.  Make sure that the expiring or expired trust certificates are no longer needed.

            -   If they are no longer required, delete them from the trust list.





