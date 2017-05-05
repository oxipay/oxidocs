<h1>Setup on Magento 1</h1>

You can install Oxipay on your site by manually copying plugin files across into your store's webserver. Use the same instructions to upgrade your existing plugin to a newer release.

## Supported Tech Stacks

Oxipay has been developed and tested against the following Magento tech stacks:

<table>
    <tr><td>Magento Version</td><td>Operating System</td><td>SQL</td><td>PHP Version</td><td>Web Server</td><tr>
    <tr><td>Magento 1.9.1.0 (CE)</td><td>Ubuntu 16.04 LTS</td><td></td><td>5.6.30</td><td>Apache 2.4.18</td><tr>
    <tr><td>Magento 1.4.2.0 (CE)</td><td>Ubuntu 14.04</td><td></td><td>5.5.9</td><td>Apache 2.4.7</td><tr>
</table>

## Plugin Installation

<div class="panel">
  You will need your <b>Merchant Number</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - You can create a backup of your store by navigating to **System** -> **Tools** -> **Backup**.

2 - Download the Oxipay plugin from [github.com/oxipay/oxipay-magento-1.x/releases](https://github.com/oxipay/oxipay-magento-1.x/releases).

3 - Unzip it, then copy the following plugin files and folders into the corresponding folder on the `app` folder on the Magento root directory.

- /app/code/community/Oxipay<br>  
- /app/design/frontend/base/default/template 
- /app/etc/modules/Oxipay_Oxipayments.xml

5 - Login into Magento's **Admin Panel**, click on **System** then select **Cache Management**.

4 - On the **Cache Management** page, click on **Flush Magento Cache**.

![3.png](/img/platforms/magento_1/3.png)

5 - Navigating to **System** > **Configuration**.

6 - On **Configuration** page, scroll downwards then click on **Payment Methods** on left side menu.

![5.png](/img/platforms/magento_1/5.png)

7 - Confirm  **Oxipay Checkout** is visible and once expanded looks similar to the image below.

<div class="panel">
  The <b>Merchant Number</b> and <b>API Key</b> have been blacked out in the image.
</div>

![6.png](/img/platforms/magento_1/6.png)

