<!-- loiofcb997f2cd864e638f187c0caa86c6db -->

# Alert Notifications

Before you can receive alert notifications during critical issues in your custom domains, you need to fulfil the following prerequisites.



<a name="loiofcb997f2cd864e638f187c0caa86c6db__prereq_esb_j2m_lzb"/>

## Prerequisites

-   A subscription of Custom Domain Manager, or an instance of the Custom Domain service.

-   A Cloud Foundry environment in the same subaccount.

-   An instance of the Alert Notification service in this Cloud Foundry environment.


> ### Note:  
> Even if you use your subaccount for only SaaS Subscriptions and subscribe to Custom Domain Manager to create the SaaS routes, you need to create a Cloud Foundry environment for the Alert Notification service.



## Context

For setting up the Alert Notification service, open the Alert Notification cockpit from the SAP BTP cockpit.



## Procedure

1.  Create a new subscription and enter a fitting *Name* and *Description*.

2.  Under *Select Conditions*, create a new condition.

    -   Enter a fitting *Name* and *Description*.

    -   Enter *Condition* `resource.tags.serviceName` *Contains* `custom-domain-service`.


3.  Under *Select Actions*, create a new action.

    -   Enter a fitting *Name* and *Description*.

    -   Select an action type of your choice.

    -   Accordingly, enter all the required values.


4.  Complete your new subscription, as documented by the Alert Notification service.

    > ### Note:  
    > You will get your first custom domain alert notification during the next scheduled daily run, and only if there are critical issues in your active configurations. Any such critical issues are also visible in the Custom Domain Manager Web UI. If you do not see any visible issues, you will get no alert notifications.


