<!-- loiobb8c0012d5074a75af60acb77888a40a -->

# Domain is not Registered for This ORG



<a name="loiobb8c0012d5074a75af60acb77888a40a__section_tlc_lj4_hdc"/>

## Scenario

You tried to create a certificate signing request and got the following error message:

```
Domain is not registered for this ORG.
```



<a name="loiobb8c0012d5074a75af60acb77888a40a__section_ulc_lj4_hdc"/>

## Reason

There are two possible reasons:

-   The domain that you tried to create a certificate signing request for, does not yet exist in your Cloud Foundry org.
-   The domain exists in another Cloud Foundry org, and when logging into Cloud Foundry, you chose the wrong Cloud Foundry org.



<a name="loiobb8c0012d5074a75af60acb77888a40a__section_e2b_wrp_fdc"/>

## Solution



### Check the Cloud Foundry ORG for the domain that you want to use

1.  Check if you are in the correct Cloud Foundry org.

    ```
    cf target
    ```

2.  Check if the domain that you want to create a certificate signing request for exists.

    ```
    cf domains
    ```

3.  If the domain does not exist, create the domain.

    ```
    cf create-domain <org> <mydomain.com>
    ```

    **Note**:If you want to use a wildcard certificate with the domain later, you don't have to add "\*." to the domain when executing this command.


