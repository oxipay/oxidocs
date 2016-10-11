# Setting up Oxipay on a WooCommerce Store

This document outlines the steps needed to install the Oxipay plugin so that it integrates with WooCommerce on your WordPress site.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    At the time of writing this document; Oxipay was developed and tested using WooCommerce version 2.6.4. Issues might be encountered if using an earlier version. If you do encounter issues, then please contact us to resolve them as soon as possible.
  </div>
</div>

## Installing the Plugin

<div class="alert alert-info" role="alert">You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation procdure.</div>

You can install the Oxipay Plugin using one of two ways: **automatically** via the WordPress Admin page, or **manually** by copying files to the WordPress server (to be performed by a web developer).

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Before proceeding with either option, please ensure that the WooCommerce plugin is properly installed and activated on you WordPress site.
  </div>
</div>

### Automatic Installation via WordPress Admin
1 - Navigate to the URL below and then click on the Download repository link; this will download a zip file; rename that .zip file to Oxipay.zip 

URL: [https://github.com/oxipay/oxipay-woocommerce/releases](https://github.com/oxipay/oxipay-woocommerce/releases)

2 - Log into the WordPress Admin page.

3 - Hover over Plugins on the left sidebar; then from the submenu that appears, click on Add New

![1.png](/img/platforms/woocommerce/1.png)

4 - This will display the Add Plugins page; click on the Upload Plugin button.

![2.png](/img/platforms/woocommerce/2.png)

5 - This will display an area on the same page where you can chose the file you want to upload.

![3.png](/img/platforms/woocommerce/3.png)

6 - Click Choose File then browse to the folder containing the Oxipay.zip file. Select it and click Open.

7 - Click on Install Now.

![4.png](/img/platforms/woocommerce/4.png)

8 - This will start the installation process. Once completed, you’ll be presented with a page confirming that the installation was successful. Then click on the Activate Plugin link.

![5.png](/img/platforms/woocommerce/5.png)

9 - Once the activation is complete, you will be re-directed to the Plugins page with a message indicating that the Plugin is activated.

![6.png](/img/platforms/woocommerce/6.png)

10 - Plugins on the page are listed alphabetically, scroll to the bottom and confirm that the Oxipay plugin is installed and activated.

![7.png](/img/platforms/woocommerce/7.png)

### Manual Installation (Performed by a Web Developer)
1 - Navigate to the URL below and then click on the Download repository link; this will download a zip file that contains the Oxipay code; rename that .zip file to Oxipay.zip.
URL: https://bitbucket.org/oxipay/oxipay-wordpress/downloads?tab=downloads

2 - Unzip the file and then copy the un-zipped folder into your WordPress server at the following path: [wordpress-folder]/wp-content/plugins

## Configuring the Plugin
1 - Log into the WordPress Admin page.

2 - Hover over Plugins on the left sidebar. From the submenu that appears, click on Installed Plugins.

![8.png](/img/platforms/woocommerce/8.png)

3 – On the Plugins page, scroll to the bottom of the page and then click on the Settings link underneath WooCommerce.

![9.png](/img/platforms/woocommerce/9.png)

4 – This will bring up the WooCommerce settings page. Click on the Checkout tab.

![10.png](/img/platforms/woocommerce/10.png)

5 – At the top of the page, click on the Oxipay link. This will bring up the various settings that can be configured for Oxipay.
Next is a description of the various settings that you will find on this page.

![11.png](/img/platforms/woocommerce/11.png)

## Description of various Oxipay Plugin Settings
**Enable**: Ticking it enables Oxipay as a payment option, otherwise it is disabled.

![12.png](/img/platforms/woocommerce/12.png)

**Test Mode**: Enables Oxipay Test Mode. Enable when instructed by Certegy to diagnose and troubleshoot possible issues with Oxipay.

![13.png](/img/platforms/woocommerce/13.png)

**Title and Description**: This controls the title and description of Oxipay that users see when selecting Oxipay as a payment option. Default values are provided which you can override.

![14.png](/img/platforms/woocommerce/14.png)

**Gateway URL**: Provided to you by Certegy. This is the URL that your site needs to communicate with to process payments using Oxipay.

![15.png](/img/platforms/woocommerce/15.png)

**API Key**: An alpha-numeric sequence provided to you by Certegy to verify that the payment request is from a current valid merchant. A new API key is generated and provided to you on a regular basis.

![16.png](/img/platforms/woocommerce/16.png)

**Merchant ID**: This is the ID that uniquely identifies your business. This value will be provided to you by Certegy.

![17.png](/img/platforms/woocommerce/17.png)

**Business Name**: The name of your business as advertised on the internet, TV or communicated to your customers via emails, brochures.

![18.png](/img/platforms/woocommerce/18.png)

Once you have finished updating the various Oxipay settings, click on the ![19.png](/img/platforms/woocommerce/19.png) button at the bottom of the page. This will then display a message at the top of the page indicating that the saving was successful.

![20.png](/img/platforms/woocommerce/20.png)

##Updates to Oxipay##

Updates to Oxipay might be made in the future to either accommodate newer internet technologies that we deem essential to integrate into our Oxipay plugin or newer versions of WooCommerce or WordPress. Our recommendation is that the existing Oxipay plugin is first deactivated and then deleted.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Deleting the existing plugin ensures that code and any associated files from the previous version of the plugin do not negatively interfere with the newer version of the plugin.
  </div>
</div>

###To delete the existing Oxipay plugin###

1 – Log into WordPress Admin.

2 – Click on Plugins on the left sidebar; then click on Installed Plugins.

3 – Scroll to the bottom, bring Oxipay into focus and then click on the Deactive link.

![21.png](/img/platforms/woocommerce/21.png)

4 – If successful, the message Plugin deactivated will be displayed at the top of the page.

![22.png](/img/platforms/woocommerce/22.png)

5 – Scroll to the bottom of the page again. This time around, click on the Delete link underneath Oxipay.

![23.png](/img/platforms/woocommerce/23.png)

6 – This will display a browser pop-up asking you to confirm if you want to proceed with deleting Oxipay.

![24.png](/img/platforms/woocommerce/24.png)

7 – This will display the plugin and the message Oxipay was successfully deleted will be displayed at the bottom of the page.

8 – You can now proceed with installing the new version of the plugin using either the manual installation procedure or automatically via WordPress as per the instructions in the Initial Installation section of this document. The URL to use to download the new version of the plugin will be provided to you by Certegy.
