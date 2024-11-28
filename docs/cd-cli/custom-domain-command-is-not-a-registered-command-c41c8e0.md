<!-- loioc41c8e069e52454dab2e262a8084de5f -->

# 'custom-domain-<command\>' is not a Registered Command



<a name="loioc41c8e069e52454dab2e262a8084de5f__section_tvz_wqp_fdc"/>

## Scenario

You tried to enter a command of the custom domain service in your command-line interface and got the following error message.

```
'<command>' is not a registered command. See 'cf help -a'


```



<a name="loioc41c8e069e52454dab2e262a8084de5f__section_dbg_xqp_fdc"/>

## Reason

You did not install the custom domain CLI plugin for the Cloud Foundry CLI.



<a name="loioc41c8e069e52454dab2e262a8084de5f__section_uvd_yqp_fdc"/>

## Solution



### Install the Custom Domain CLI Plugin

A prerequisites for the installation of the custom domain CLI plugin is that you have installed the Cloud Foundry CLI. You can download the Cloud Foundry CLI [here](https://github.com/cloudfoundry/cli#downloads).

1.  Download the latest version of the plugin that is compatible with your operating system. On this [page](https://tools.hana.ondemand.com/#cloud), you'll find the plugin, called Custom Domain, under the SAP BTP, Cloud Foundry CLI plugins section.
2.  Untar or unzip the downloaded archive.
3.  Open the command-line interface or terminal.
4.  To install the plugin, enter the following command:

    Mac and Linux:

    ```
    cf install-plugin <path to the downloaded folder>/custom-domain-cli
    ```

    Windows:

    ```
    cf install-plugin <path to the downloaded folder>\custom-domain-cli.exe
    ```

5.  Verify that the plugin has been installed successfully by entering:

    ```
    cf plugins
    ```


