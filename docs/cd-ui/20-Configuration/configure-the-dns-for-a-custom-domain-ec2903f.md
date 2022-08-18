<!-- loioec2903f6c1a7400aabd77fbbbdefa25b -->

# Configure the DNS for a Custom Domain

To route traffic to an application on your custom domain, you must also configure the Domain Name System \(DNS\) that you use. **However, as a customer, you also have the choice to run under SAP's standard domain as a subdomain. In such cases, your own DNS records are not required.**



<a name="loioec2903f6c1a7400aabd77fbbbdefa25b__context_fc5_bbc_mgb"/>

## Context

For each custom domain you want to use, you must create a CNAME mapping from the custom domain to its Cloud Foundry domain. This mapping is specific for each domain name provider that you are using. Usually, you can modify CNAME records using the administration tools available from your domain name registrar.



<a name="loioec2903f6c1a7400aabd77fbbbdefa25b__steps_gc5_bbc_mgb"/>

## Procedure

1.  Sign in to the administrative tool of your domain name registrar and find the place where you can update the domain DNS records.

2.  Locate and update the CNAME records for your custom domain to point to your Cloud Foundry API, for example: **api.cf.eu10.hana.ondemand.com**.

    If your custom domain is for example, **applications.example.com** and your Cloud Foundry API is **api.cf.eu10.hana.ondemand.com**, create a CNAME record with the name **\*.applications** and the alias **api.cf.eu10.hana.ondemand.com**. After this configuration is active, you can route applications from **api.cf.eu10.hana.ondemand.com** to **applications.example.com**.

    > ### Note:  
    > If your provider doesn't allow creating a CNAME record with a wildcard, you have to create a single entry for each application under your custom domain, for example **myapp.applications.example.com**, **myapp2.applications.example.com** and so on.
    > 
    > Depending on your provider, it may take several hours for the changes to take effect. For further details, consult your domain name registrar documentation.


