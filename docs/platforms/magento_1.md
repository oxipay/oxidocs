<h1>Setup on Magento 1</h1>

You can install Oxipay plugin by manually copying plugin files across into your store's webserver. <br>
Use the same instructions to upgrade your existing plugin to a newer release.

## Supported Tech Stacks

Oxipay has been developed and tested against the following Magento tech stacks:

| Magento Version      | Operating System | SQL    | PHP Version | Web Server    |
|----------------------|------------------|--------|-------------|---------------|
| Magento 1.9.1.0 (CE) | Ubuntu 16.04 LTS | 5.5.55 | 5.6.30      | Apache 2.4.18 |
| Magento 1.4.2.0 (CE) | Ubuntu 14.04 LTS | 5.5.54 | 5.5.9       | Apache 2.4.7  |


## Plugin Installation

<div class="panel">
  You will need your <b>Merchant Number</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - You can create a backup of your store by navigating to **System** -> **Tools** -> **Backup**.

2 - Download the Oxipay plugin from [github.com/oxipay/oxipay-magento-1.x/releases](https://github.com/oxipay/oxipay-magento-1.x/releases).

3 - Unzip it, then copy the following plugin files and folders into the corresponding folders under the Magento root directory.

- /app/code/community/Oxipay
- /app/design/frontend/base/default/template/oxipayments
- /app/design/adminhtml/base/default/template/oxipayments
- /app/etc/modules/Oxipay_Oxipayments.xml

- /skin/frontend/base/default/images/Oxipay/
- /skin/adminhtml/base/default/images/Oxipay/

4 - Login into Magento's **Admin Panel**, click on **System** then select **Cache Management**.

5 - On the **Cache Management** page, click on **Flush Magento Cache**.

![3.png](/img/platforms/magento_1/3.png)

## Configuration

1 - Navigating to **System** > **Configuration**.

2 - On **Configuration** page, scroll downwards then click on **Payment Methods** on left side menu.

![5.png](/img/platforms/magento_1/5.png)

3 - Confirm  **Oxipay Checkout** is visible and once expanded looks similar to the image below.

![6.png](/img/platforms/magento_1/6.png)

