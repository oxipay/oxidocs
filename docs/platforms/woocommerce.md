<h2>Setup on WooCommerce</h2>

You can install Oxipay automatically by uploading the plugin or manually by copying plugin files. Use the same instructions to upgrade your existing plugin to a newer release.

## Supported Tech Stacks

The plugin has been developed and tested against the following Magento tech stacks:

<table style="font-size:1.1rem">
    <tr><td>Magento Platform</td><td>Operating System</td><td>MySQL</td><td>PHP Version</td><td>Web Server</td><tr>
    <tr><td>Magento 1.9.1.0 (CE)</td><td>Ubuntu 16.04 LTS</td><td>14.14</td><td>5.6.30</td><td>Apache 2.4.18</td><tr>
    <tr><td>Magento 1.4.2.0 (CE)</td><td>Ubuntu 14.04</td><td>14.14</td><td>5.5.9</td><td>Apache 2.4.7</td><tr>
</table>

## Automatic Installation

<div class="panel">
  You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - Download the plugin from [github.com/oxipay/oxipay-woocommerce/releases](https://github.com/oxipay/oxipay-woocommerce/releases).

2 - Log into **WordPress Admin** then click on **Plugins** on the left menu.

3 - This will take you to the **Plugins** page; click on **Add New** on the top left.

4 - This will take you to the **Add Plugins** page; click on **Upload Plugin** on the top left.

5 - Click **Choose File** on the form that appears, select the Oxipay plugin and then click **Install Now**.

6 - This will begin the installation. Once complate, click on **Activate Plugin**.

7 - This will take you to the **Plugins** page with a **Plugin activated** message at the top.

8 - Examine installed plugins and confirm Oxipay is installed and activated.

![23.png](/img/platforms/woocommerce/23.png)

## Manual Installation

<div class="panel">
  We recommend manual installation be performed by an IT professional or a Web Developer.
</div>

1 - Download the plugin from [github.com/oxipay/oxipay-woocommerce/releases](https://github.com/oxipay/oxipay-woocommerce/releases).

2 - Unzip it then copy the files into your WordPress server at the following path: [wordpress-folder]/wp-content/plugins

<h2>Oxipay Settings</h2>

Open WooCommerce's **Settings** page, click on **Checkout** then on **Oxipay**.

![11.png](/img/platforms/woocommerce/11.png)

Below is a description of the various settings you will find there.

**Enabled**: Enables or disables Oxipay

**Title**: Title for Oxipay that is displayed on checkout screen.

**Description**: Description for Oxipay that is displayed on checkout screen.

**Shop Name**: Your online store's name as displayed on the Internet or TV.

**Oxipay Gateway URL**: URL that your site communicates with to process payments over Oxipay.

**Merchant ID**: Identifies your business and provided as part of your onboarding.

**API Key**: Code used to verify that payment requests from your site are valid. 