<!-- loio8f845329f83f402eb59e8d3b7735754b -->

# Remove the Custom Domain Service Instance

Use the Cloud Foundry command-line interface to remove the custom domain service instance from your Cloud Foundry organization.



## Procedure

1.  Delete the Custom Domain service instance:

    ```
    cf delete-service <Service Instance Name>
    ```

    > ### Sample Code:  
    > ```
    > cf delete-service custom-domain-service
    > ```

    > ### Restriction:  
    > You can't perform any commands from the Custom Domain service during the deletion process.

    > ### Note:  
    > `custom-domain-service` is an example for the name, that you have given your service instance. Type `cf services` to look up the name that you have given the custom domain service instance.

2.  Confirm the deletion process.

3.  Verify that the service instance has been deleted:

    ```
    cf services
    ```

    > ### Note:  
    > It can take until the next day to complete the deletion process. During the deletion process, the column **last operation** shows ***"delete in progress"***. The timezone depends on the region of your Cloud Foundry environment.




<a name="loio8f845329f83f402eb59e8d3b7735754b__result_z5x_d34_hhb"/>

## Results

If the service instance is not listed under services anymore, you have successfully deleted the service instance from your Cloud Foundry organization.

**Related Information**  


[Create the Service Instance with the Cloud Foundry CLI](10-Initial/create-the-service-instance-with-the-cloud-foundry-cli-8eef2cc.md "To use the Custom Domain service for your applications, use the Cloud Foundry CLI to create a service instance for your Cloud Foundry organization.")

