<!-- loioe252d2631f7a472dabc410aabf2f8c13 -->

# Best Practices for Configuration Changes

To avoid downtimes caused by the deactivation of SANs, TLS configuration changes can be made by using alternative approaches to mitigate such situations.



<a name="loioe252d2631f7a472dabc410aabf2f8c13__context_ojx_qkv_brb"/>

## Context

Depending on whether you expect to change your TLS configurations frequently \(for example, to add or remove trusted CAs, manage the TLS versions, or determine the cipher suites\) or only once, you can use the one of the following methods.

-   For frequent TLS configuration changes:

    1.  Have two TLS configurations; with one of them being used by activated server certificate SANs, while the other one is unused.

    2.  Edit the unused one, as required.

    3.  Now, switch to the *Server Certificates* tile to activate all the SANs and select the unused one as the new TLS configuration.

        > ### Note:  
        > This renders the first one as the unused configuration now.

    4.  When the next update needs to be done follow the same process of editing the unused one, which then replaces the other configuration that is currently in use.



-   For a one-time TLS configuration change:

    1.  Clone the currently used TLS configuration.

    2.  Edit the clone, as required.

    3.  Now, switch to the *Server Certificates* tile to activate all the SANs and select the clone as the new TLS configuration that should be used.

        > ### Note:  
        > The original TLS configuration is unused now. If it is no longer needed, you can also delete it.



