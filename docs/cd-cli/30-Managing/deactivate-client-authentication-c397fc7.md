<!-- loioc397fc768cd9464fa7694ce4e1d003e7 -->

# Deactivate Client Authentication

Use the Cloud Foundry CLI to deactivate client authentication for specific custom domains. As a result, your applications under those domains can be accessed without the need of client authentication.



## Procedure

1.  Log in to your Cloud Foundry account:

    ```
    cf login
    ```

2.  Enter your credentials.

3.  Deactivate the client authentication:

    ```
    cf custom-domain-disable-client-authentication <Custom Domain>
    ```

    > ### Sample Code:  
    > ```
    > cf custom-domain-disable-client-authentication *.applications.example.com
    > ```

    > ### Note:  
    > You can't disable client authentication for more than one custom domain at a time using this command.

4.  Check the status of your custom domains:

    ```
    cf custom-domain-list
    ```

    > ### Note:  
    > From the moment that client authentication is listed as disabled, it can take until the next day to process the deactivation. The timezone depends on the region of your Cloud Foundry environment.


