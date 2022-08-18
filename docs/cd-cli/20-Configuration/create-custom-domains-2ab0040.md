<!-- loio2ab0040222ce4c018dfe798be13be379 -->

# Create Custom Domains

To make your applications reachable and secure under your own domain, use the Cloud Foundry CLI to create your custom domains.



## Procedure

1.  Log on to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Create your custom domain:

    ```
    cf create-domain <Cloud Foundry Org> <Custom Domain>
    ```

    -   If you want to create a domain called `example.com`:

        > ### Sample Code:  
        > ```
        > cf create-domain myOrg example.com
        > ```

    -   If you want to create a domain called `example.com` with a subdomain called `applications`:

        > ### Sample Code:  
        > ```
        > cf create-domain myOrg applications.example.com
        > ```


    > ### Note:  
    > -   Create each custom domain separately; that is, you can’t create multiple domains with a single command.
    > 
    > -   If you want to use a wildcard certificate with the domain later, you don't have to add "\*." to the domain when executing this command.

4.  Verify that your domain has been created:

    ```
    cf domains
    ```


