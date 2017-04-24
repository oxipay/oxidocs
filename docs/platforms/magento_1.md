# Setting up Oxipay on a Magento 1 Store

  The plugin was developed and tested against Magento Community Edition version 1.9 and 1.4

<div class="panel">
  You will need your Merchant ID and API Key before continuing with the installation. If you haven't received both yet, contact us at <a href="mailto:support@oxipay.com.au?Subject=Merchant ID">support@oxipay.com.au</a>.
</div>

## Installation

1 - To create a backup of your store, you can do so by navigating to **System** -> **Tools** -> **Backup**.

2 - Download the plugin from [github.com/oxipay/oxipay-magento-1.x/releases](https://github.com/oxipay/oxipay-magento-1.x/releases).

3 - Unzip the downloaded plugin, then copy the following files and folders into the corresponding folder on the `app` folder on the Magento root directory.

- /app/code/community/Oxipay<br>  
- /app/design/frontend/base/default/template 
- /app/etc/modules/Oxipay_Oxipayments.xml

5 - Login into Magento's **Admin Panel**, click on **System** then select **Cache Management**.

4 - On the **Cache Management** page, click on **Flush Magento Cache**.

![3.png](/img/platforms/magento_1/3.png)

5 - Confirm the plugin has been installed by navigating to **System** > **Configuration**.

6 - On **Configuration** page, scroll downwards then click on **Payment Methods** on left side menu.

![5.png](/img/platforms/magento_1/5.png)

7 - Confirm  **Oxipay Checkout** is visible and once expanded looks similar to the image below.


![6.png](/img/platforms/magento_1/6.png)

<div class="panel">
  The <b>Merchant Key</b> and <b>API Key</b> have been blacked out in the image.
</div>

##Upgrading the Plugin##

1 - Download newer release and perform installation outlined above by overriding existing Oxipay files in your Magento directory with the same files from the newer plugin release.

<div class="panel">
  Existing Oxipay settings such as the <b>Merchant Number</b> for instance will be retained after you have performed the upgrade.
</div>

2 - Login into Magento's **Admin Panel**, click on **System** then select **Cache Management**.

3 - Click on **Flush Cache Storage** on the top right.
