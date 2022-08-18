<!-- loio9f98dd0fcf9447019f233403f4ca60c1 -->

# Install the Custom Domain Plugin

Use the Custom Domain CLI plugin to configure and manage your custom domains.



## Prerequisites

Install the Cloud Foundry command-line interface \(CLI\) for the plugin to work. You can find the installation instructions here: [Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Dev/en-US/4ef907afb1254e8286882a2bdef0edf4.html "Download and set up the Cloud Foundry Command Line Interface (cf CLI) to start working with the Cloud Foundry environment.") :arrow_upper_right:.



## Procedure

1.  Download the latest version of the plugin that is compatible with your operating system. On the [Web page](https://tools.hana.ondemand.com/#cloud), you'll find the plugin under the **SAP BTP Cloud Foundry CLI plugins** section with the name Custom Domain.

2.  Untar or unzip the downloaded archive.

3.  Open the command-line interface or terminal.

4.  To install the plugin, enter the following command:

    -   Mac and Linux:

        ```
        cf install-plugin <path to the downloaded folder>/custom-domain-cli
        ```

    -   Windows:

        ```
        cf install-plugin <path to the downloaded folder>\custom-domain-cli.exe
        ```


    > ### Note:  
    > If you are reinstalling the plugin, first uninstall the previous version using: `cf uninstall-plugin "Custom Domain"` 

5.  Verify that the plugin has been installed successfully by entering:

    ```
    cf plugins
    ```

    You see a list of plugins that now includes Custom Domain. The output also displays commands that are specific to the Custom Domain plugin.




<a name="loio9f98dd0fcf9447019f233403f4ca60c1__result_cl2_wck_pgb"/>

## Results

You have installed the Custom Domain plugin for the Cloud Foundry CLI and can now use the extended commands that are available from the Custom Domain service.

**Related Information**  


[Download and Install the Cloud Foundry Command Line Interface](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Dev/en-US/4ef907afb1254e8286882a2bdef0edf4.html "Download and set up the Cloud Foundry Command Line Interface (cf CLI) to start working with the Cloud Foundry environment.") :arrow_upper_right:

[Configuring Custom Domains](../20-Configuration/configuring-custom-domains-1c6c729.md "To make sure that your domain is trusted and all application data is protected, you must first set up secure TLS/SSL communication. Then, make your application reachable via the custom domain and route traffic to it.")

