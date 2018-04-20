<h1>Setup on OpenCart</h1>

You can install Oxipay automatically with the extension installer or manually by copying the extension files. Use the same instructions to upgrade your existing extension to a newer release.

Supported OpenCart Versions:

 * v2.x
 * v3.0.x

<div class="panel">
  You will need your <b>Merchant ID</b> and an <b>Encryption Key (API Key)</b> handy before continuing with the installation.
</div>

## Extension Installer

<div class="panel">
  The Extension Installer requires FTP settings to be already configured with-in OpenCart. If this is not already done we recommend following the Manual Installation steps below.
</div>

1 - Download the Oxipay extension from [github.com/oxipay/oxipay-opencart/releases](https://github.com/oxipay/oxipay-opencart/releases).

2 - Log into your **OpenCart Admin**, click on **Extensions** on the left menu then on **Extension Installer** in the submenu item below.

![5.png](/img/platforms/opencart/5.png)

3 - Click the **Upload** button and select the Oxipay extension installation file (it will end with `.ocmod.zip`); Click the 'Continue' button. 

_Next: Continue onto Complete The Install instructions below._

## Manual Installation

1 - Download the Oxipay extension from [github.com/oxipay/oxipay-opencart/releases](https://github.com/oxipay/oxipay-opencart/releases).

2 - Unzip it and copy the contents of the `uploads` folder into OpenCarts root folder. For a new install no files should be overwriten, with an upgrade only previous Oxipay files should be overwritten.

_Next: Continue onto Complete The Install instructions below._

## Complete The Install

1 - If not already log into your **OpenCart Admin**; From the left menu select **Extensions** and then **Extensions** submenu item below.

![1.png](/img/platforms/opencart/1.png)

2 - This will take you to the **Extensions** page; Select **Payments** from the extension type dropdown.

![2.png](/img/platforms/opencart/2.png)

3 - Locate Oxipay and click the **Install** icon on the right.

![3.png](/img/platforms/opencart/3.png)

4 - Still on Oxipay, now click on the **Edit** icon on th right, this will open the Oxipay settings page.

5 - Ensure that at the bottom of the page, the **Status** setting is set to **Enabled**, that the other settings are configured as below, then click on **Save**.

![6.png](/img/platforms/opencart/6.png)

## Configuration

Browse to the **Payment Extensions** listing page *(see above steps 3-4)*; Locate Oxipay and click the **Edit** icon on the right

![4.png](/img/platforms/opencart/4.png)

Below is a description of the various settings you will find on the Oxipay settings page.

**Display Details**

Setting | Description
--- | ---
Title | Title for Oxipay that is displayed on checkout screen
Description | Description for Oxipay that is displayed on checkout screen

**Shop Details**

Setting | Description
--- | ---
Shop Name | Your online store's name as displayed on the Internet or TV
Oxipay Region | The Oxipay region your store operates in

**Gateway Settings**

Setting | Description
--- | ---
Oxipay Environment | Select which environment to use: Sandbox (Test) / Live or Other. Sandbox should be used for payment tests.
Oxipay Gateway URL | Only shown if Oxipay Environment is set to Other. Allows a custom Gateway URL to be specified.
Merchant ID | Identifies your business and is provided as part of your onboarding
API Key | Code used to verify that payment requests from your site are valid

<div class="panel">
  The Oxipay Platform Integration Team will provide you with your API key.
</div>

**General Settings**

Setting | Description
--- | ---
Order Status Completed | Status orders will be set to when payment is marked as completed.<br><br>We recommend setting this to 'Completed'.
Order Status Pending | Status orders will be set to when payment is marked as pending.<br><br>We recommend setting this to 'Processing'.
Order Status Failed | Status orders will be set to when payment is marked as failed.<br><br>We recommend setting this to 'Failed'.
Geo Zone | Select the Geo Zone this payment will be visible in.
Status | Enables or disables Oxipay
Sort Order | If you have more than one payment gateway, please use this field to define the order they are shown in. A setting of '1' will show it first, '2' second, etc.
