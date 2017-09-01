<h1>Setup on WooCommerce</h1>

You can install EPCarts automatically by uploading the plugin or manually by copying plugin files. Use the same instructions to upgrade your existing plugin to a newer release.

## Plugin Installation

<div class="panel">
  You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 - Download the plugin from [github.com/EPCarts/EPCarts-woocommerce/releases](https://github.com/EPCarts/EPCarts-woocommerce/releases).

2 - Log into **WordPress Admin** then click on **Plugins** on the left menu.

3 - This will take you to the **Plugins** page; click on **Add New** on the top left.

4 - This will take you to the **Add Plugins** page; click on **Upload Plugin** on the top left.

5 - Click **Choose File** on the form that appears, select the EPCarts plugin and then click **Install Now**.

6 - This will begin the installation. Once complate, click on **Activate Plugin**.

7 - This will take you to the **Plugins** page with a **Plugin activated** message at the top.

8 - Examine installed plugins and confirm EPCarts is installed and activated.

![23.png](/img/platforms/woocommerce/23.png)

## Configuration

Open WooCommerce's **Settings** page, click on **Checkout** then on **EPCarts**.

![11.png](/img/platforms/woocommerce/11.png)

Below is a description of the various settings you will find in the EPCarts settings page.

**Enabled**: Enables or disables EPCarts

**Title**: Title for EPCarts that is displayed on checkout screen.

**Description**: Description for EPCarts that is displayed on checkout screen.

**Shop Name**: Your online store's name as displayed on the Internet or TV.

**EPCarts Gateway URL**: The EPCarts gateway that the plugin would need to communicate with for it to process payments via EPCarts.

| EPCarts Environment | URL  |
|--------------------|------|
| Production Gateway | https://secure.%domain%/Checkout?platform=WooCommerce |
| Sandbox Gateway    | https://securesandbox.%domain%/Checkout?platform=WooCommerce |

**Merchant ID**: Identifies your business and is provided as part of your onboarding.

**API Key**: Code used to verify that payment requests from your site are valid. 
<div class="panel">
  The EPCarts Platform Integration Team will provide you with your API key over the phone.
</div>
