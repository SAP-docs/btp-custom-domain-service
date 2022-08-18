<!-- loioda9b54e5b9b54fbaa2b381af2bd15bc8 -->

# Configure the DNS for a Custom Domain

To route traffic to an application on your custom domain, you must also configure the Domain Name System \(DNS\) that you use.



<a name="loioda9b54e5b9b54fbaa2b381af2bd15bc8__context_fc5_bbc_mgb"/>

## Context

For each custom domain you want to use, you must create a CNAME mapping from the custom domain to its Cloud Foundry domain. This mapping is specific for each domain name provider you are using. Usually, you can modify CNAME records using the administration tools available from your domain name registrar.



<a name="loioda9b54e5b9b54fbaa2b381af2bd15bc8__steps_gc5_bbc_mgb"/>

## Procedure

1.  Sign in to the administrative tool of your domain name registrar and find the place where you can update the domain DNS records.

2.  Locate and update the CNAME records for your custom domain to point to your Cloud Foundry API, for example: **api.cf.eu10.hana.ondemand.com**. You can look up the API by executing the command:

    ```
    cf api
    ```

    If your custom domain is for example, **applications.example.com** and your Cloud Foundry API is **api.cf.eu10.hana.ondemand.com**, create a CNAME record with the name **\*.applications** and the alias **api.cf.eu10.hana.ondemand.com**. After this configuration is active, you can route applications from **api.cf.eu10.hana.ondemand.com** to **applications.example.com**.

    > ### Note:  
    > If your provider doesn't allow creating a CNAME record with a wildcard, you have to create a single entry for each application under your custom domain, for example **myapp.applications.example.com**, **myapp2.applications.example.com** and so on.

3.  Check if the CNAME configuration is active:

    -   On Mac and Linux, open the terminal and type:

        For a wildcard entry:

        ```
        dig *.<Custom Domain>
        ```

        > ### Sample Code:  
        > ```
        > dig *.applications.example.com
        > ```

        If you see your custom domain pointing to your Cloud Foundry domain under ***ANSWER SECTION***, the DNS is configured.

    -   On Windows, open the command-line tool and type:

        For a wildcard entry:

        ```
        nslookup *.<Custom Domain>
        ```

        > ### Sample Code:  
        > ```
        > nslookup *.applications.example.com
        > ```

        If you see your custom domain under ***Aliases***, the DNS is configured.


    > ### Note:  
    > Depending on your provider, it may take several hours for the changes to take effect. For further details, consult your domain name registrar documentation.


