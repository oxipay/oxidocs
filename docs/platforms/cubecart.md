# Setting up %product_name% on a CubeCart Store

This document outlines the steps needed to install %product_name% on your CubeCart Store.

<div class="panel">
  At the time of writing this article, %product_name% was developed and tested against CubeCart version <code>6.1.1</code>, although the plugin should be compatible with other CubeCart versions. If you encounter any issues, please contact us to resolve them as soon as possible.
</div>

## Installing %product_name%

<div class="panel">
  You will need a <b>Merchant ID</b> and <b>API Key</b> before continuing with the installation procedure. They are required to uniquely identify the Merchant and provide a secure link. If you don't have either of these, please contact <a href="mailto:support@%domain%">support@%domain%</a>
</div>

The plugin can be installed via CubeCart's Admin Control Panel, either manually or automatically using a Token. This section details how to upload the plugin, and install and configure its various parameters for it to work properly.

<div class="panel">
  If you have trouble accessing your CubeCart's Admin Control Panel, please consult CubeCart's official <a href="https://support.cubecart.com/Knowledgebase/List">knowledgebase</a> and <a href="https://forums.cubecart.com/">forums</a>, or your IT department to resolve the issue.
</div>

### Automatic Installation using Token

**1** - Navigate to the following URL.

[https://www.cubecart.com/extensions/payment-gateways/%class_name%](https://www.cubecart.com/extensions/payment-gateways/%class_name%)

**2** - Select the **lightning bolt** button, next to your required %product_name% plugin version, to reveal the **Auto Install/Upgrade Token**

![autoinstall-1.png](/img/platforms/cubecart/autoinstall-1.png)

**3** - Copy the **Token** from within the pop-up.

![autoinstall-2.png](/img/platforms/cubecart/autoinstall-2.png)

**4** - Log into the CubeCart Admin Control Panel as an Administrator.

![autoinstall-3.png](/img/platforms/cubecart/autoinstall-3.png)

**5** - Once logged in, you will be presented with your Store's dashboard. From the side menu that appears to the left, scroll to the **Extensions** section and select **Manage Extensions**.

![autoinstall-4.png](/img/platforms/cubecart/autoinstall-4.png)

**6** - Copy the **Auto Install/Upgrade Token** into the Token field on the **Manage Extensions** page and select the **Go** button.

![autoinstall-5.png](/img/platforms/cubecart/autoinstall-5.png)

**7** - If the module has been installed correctly, the module will appear in the list of **Available Extensions**.

![autoinstall-6.png](/img/platforms/cubecart/autoinstall-6.png)

<div class="panel">
If the automatic installation is not successful, you will be presented with a message at the top of the page similar to the screenshot below. If this continues to be a problem, please refer to the <a href="#manual-installation">Manual Installation</a> procedure.
</div>

![autoinstall-7.png](/img/platforms/cubecart/autoinstall-7.png)

### Manual Installation

**1** - Navigate to the following URL.

[https://www.cubecart.com/extensions/payment-gateways/%class_name%](https://www.cubecart.com/extensions/payment-gateways/%class_name%)

**2** - Select the **download** button , next to your required %product_name% plugin version, to download the %product_name% plugin ZIP file.

![manualinstall-1.png](/img/platforms/cubecart/manualinstall-1.png)

**3** - Extract the ZIP file and copy the contents to the **modules/gateway** folder of your server’s/site directory.

**4** - Ensure the folders/files have adequate read/write permissions set.

**5** - Log into the CubeCart Admin Control Panel as an Administrator.

![manualinstall-2.png](/img/platforms/cubecart/manualinstall-2.png)

**6** - Once logged in, you will be presented with your Store's dashboard. From the side menu that appears to the left, scroll to the **Extensions** section and select **Manage Extensions**.

![manualinstall-3.png](/img/platforms/cubecart/manualinstall-3.png)

**7** - If the module has been installed correctly, the module will appear in the list of **Available Extensions**.

![manualinstall-4.png](/img/platforms/cubecart/manualinstall-4.png)

## Configuring %product_name%

<div class="panel">
  This section describes the <b>Module Settings</b> available once you have installed the %product_name% plugin. This includes the %product_name% gateways to communicate with, as well as whether or not to enable Test Mode.  
</div>

**1** - Log into the CubeCart Admin Control Panel as an Administrator.

**2** - Once logged in, you will be presented with your Store's dashboard. From the side menu that appears to the left, scroll to the **Extensions** section and select **Manage Extensions**.

**3** - Under the **Available Extensions** section, select the text **%product_name%** to configure the module settings. Descriptions of the options are listed below.

![config-1.png](/img/platforms/cubecart/config-1.png)
<div class="panel">
  We have intentionally masked the <b>Merchant ID</b> and <b>API Key</b> in this support document. Please contact us and we will advise you of the settings to use.
</div>

<hr>

* **Status** This must be enabled for the payment options to appear during checkout.
<hr>

* **Priority** 	If you have more than one payment gateway, please use this field to define the order they are shown in. A setting of '1' will show it first, '2' second, etc.
<hr>

* **Scope** This allows you to specify whether you want the %product_name% plugin to be available via the Main Website only or the Mobile Website only, or both.
<hr>

* **Default** This must be enabled if you would like %product_name% pre-selected for the Customer as the default payment option.
<hr>

* **Merchant ID** This is the %product_name% Merchant ID that you are provided with as part of your on-boarding when signing-up for %product_name%.
<hr>

* **API Key** The API Key or the Encryption key is a case-sensitive alpha-numeric sequence that is used to authenticate payment requests originating from your Store. It is vital that you protect it and don't provide it to unauthorised individuals.
<hr>

* **Test Mode** Indicates whether to process payments over the live %product_name% Gateway URL resulting in real transactions, or to process it over the %product_name% Sandbox Gateway URL which will produce simulated (test) transactions with no real dollar amounts being debited. By default it should be set to **No** unless we are attempting to diagnose issues on your store to do with %product_name%, or you're testing integrating the plugin with your online CubeCart store.
<hr>

* **Test Gateway URL** This specifies the test %product_name% end-point that the plugin would need to communicate with when **Test Mode** is enabled. This is mainly used for troubleshooting purposes, particularly if we want to simulate test transactions on your CubeCart Store without having real dollar amounts debited from Credit Cards.
<hr>

* **Gateway URL** This specifies the live %product_name% end-point that the plugin would need to communicate with for it to be able to process payments via %product_name%. Note that transactions processed over this URL are real transactions that end up in real dollar amounts being deducted.

<hr>

**4** - Once you have finished making the necessary configuration changes, click the **Save** button.

**5** - **%country%** will be automatically set as an **Enabled Region** in the **Allowed Zones** tab. This must match the Country set in the CubeCart Store Settings.

![config-2.png](/img/platforms/cubecart/config-2.png)
<hr>

<hr>

##Upgrading %product_name%

###Automatic Upgrade

<div class="panel">
Importantly, when you perform an automatic upgrade, all the module settings are retained.
That is, you do not need to type in your <b>Merchant ID</b> and <b>API Key</b> again.
</div>

**1** - Navigate to the following URL.

[https://www.cubecart.com/extensions/payment-gateways/%class_name%](https://www.cubecart.com/extensions/payment-gateways/%class_name%)

**2** - Select the **lightning bolt** button, next to your required %product_name% plugin version, to reveal the **Auto Install/Upgrade Token**

![autoinstall-1.png](/img/platforms/cubecart/autoinstall-1.png)

**3** - Copy the **Token** from within the pop-up.

![autoinstall-2.png](/img/platforms/cubecart/autoinstall-2.png)

**4** - Log into the CubeCart Admin Control Panel as an Administrator.

![autoinstall-3.png](/img/platforms/cubecart/autoinstall-3.png)

**5** - Once logged in, you will be presented with your Store's dashboard. From the side menu that appears to the left, scroll to the **Extensions** section and select **Manage Extensions**.

![autoinstall-4.png](/img/platforms/cubecart/autoinstall-4.png)

**6** - Copy the **Auto Install/Upgrade Token** into the Token field on the **Manage Extensions** page.

![autoinstall-5.png](/img/platforms/cubecart/autoinstall-5.png)

**7** - If you enable the option to **Backup if already exists**, a backup of the previous plugin version will be created.

**8** - Select the **Go** button to complete the upgrade.

<hr>

###Manual Upgrade

<div class="panel">
Prior to manually upgrading, you will first need to un-install the previous version.
</div>


##Un-installing %product_name%

**1** - Log into the CubeCart Admin Control Panel as an Administrator.

![uninstall-1.png](/img/platforms/cubecart/uninstall-1.png)

**2** - Once logged in, you will be presented with your Store's dashboard. From the side menu that appears to the left, scroll to the **Extensions** section and select **Manage Extensions**.

![uninstall-2.png](/img/platforms/cubecart/uninstall-2.png)

**3** - In the list of **Available Extensions**, select the **delete** button associated with the **%product_name%** extension.

**4** - If the module has been un-installed correctly, the module will no longer appear in the list of **Available Extensions**.

![uninstall-3.png](/img/platforms/cubecart/uninstall-3.png)

**5** - You can now download the new version of the %product_name% CubeCart plugin and install it as per the instructions in the [Installing %product_name%](#installing-%class_name%) section of this document.
