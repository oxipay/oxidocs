# Setting up Oxipay on a Magento 1 Store

This document outlines the steps needed to integrate the Oxipay Payment Gateway into your Magento store.

**NOTE** At the time of writing this article; Oxipay was developed and tested using Magento Community Edition 1.9. Issues might be encountered if using an earlier version. If you do encounter issues, then please contact us to resolve them as soon as possible.

## Installing the Plugin

<div class="alert alert-info" role="alert">You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation procdure.</div>

You can install the Oxipay Plugin manually by copying the Oxipay Magento plugin code that is provided to you into the Magento root folder. 

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Performing the steps underneath requires solid knowledge of the Magento platform as well as the computer file systems in general. We recommend that an IT professional or a web developer perform these steps to avoid any unintended damage to the existing Magento installation.
  </div>
</div>

1 - Navigate to the URL below and then click on the Download repository link; this will download a zip file; rename that .zip file to Oxipay.zip

URL: [https://github.com/oxipay/oxipay-magento-1.x/releases](https://github.com/oxipay/oxipay-magento-1.x/releases)

2 - Unzip the Oxipay.zip folder and then copy the app folder into your Magento store root directory.

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Before proceeding with the remainder of the installation procedure, ensure that you have a current back of your Magento store. To create a backup, navigate to System -> Tools -> Backup. This is useful in the event you encounter issues with installing Oxipay.
  </div>
</div>

3 - Copy all files in the unzipped Oxipay folder <code>Oxipay/app</code> into the <code>/app</code> folder in your Magento root folder.

4 - Login into the Magento **Admin Panel**, then from within the **Admin Panel** menu click on **System**.

![1.png](/img/platforms/magento_1/1.png)

5 - This will open up the **System** menu. Click on **Cache Management**.

Login into Magento **Admin Panel** and then navigate to **System** > **Cache Management**.

![2.png](/img/platforms/magento_1/2.png)

6 - From within the **Cache Management** page, click on the **Flush Magento Cache** button in the top right.

![3.png](/img/platforms/magento_1/3.png)

7 - Confirm that Oxipay has been installed on your Magento Store. To do this, click on **System** in the **Admin Panel** then on **Configuration**.

![4.png](/img/platforms/magento_1/4.png)

8 - This will open up the **Configuration** page, scroll to the bottom and then click on **Payment Methods** on the left side menu.

![5.png](/img/platforms/magento_1/5.png)

9 - Confirm that Oxipay Checkout is visible as a Payment Method and once expanded it looks similar to the image below.

![6.png](/img/platforms/magento_1/6.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    The <b>Merchant Key</b> and <b>API Key</b> have been blacked out in the image above.
  </div>
</div>

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Missing fields might indicate that some of the Oxipay files that were downloaded as part of the installation process might have been corrupted inadvertently somewhere in the process.
  </div>
</div>

##Updates to Oxipay##

Updates to Oxipay might be made in the future to either accommodate newer internet technologies that we deem essential to integrate into our Oxipay plugin or newer versions of Magento 1.x that include security or feature patches. We recommend that you first unintall the existing Oxipay plugin before installing a newer Oxipay version.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Deleting the existing plugin ensures that code and any associated files from the previous version of the plugin do not negatively interfere with the newer version of the plugin.
  </div>
</div>

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    At the time of writing this article, Oxipay can only be deleted by manually deleting the Oxipay specific folders and files that were integrated into Magento as part of the installation procedure.
  </div>
</div>

1 - Open the <code>app</code> folder inside the Magento root folder where you have installed your version of Magento and delete the files and folder paths listed underneath:

Folders:

* <code>app\code\community\Oxipay</code>
* <code>app\design\frontend\base\default\template\oxipayments</code>

Files:

* <code>app\etc\modules\Oxipay_Oxipayments.xml</code>

2 - Login to **Magento Admin** and then navigate to **System** then **Cache Management**.

![2.png](/img/platforms/magento_1/2.png)

3 - On the top right, click on Flush Cache Storage to clear Magento's cache.

![3.png](/img/platforms/magento_1/3.png)

4 - Now you can proceed with installing the new version of the Oxipay plugin by following the [Installing the Plugin](magento_1.md#Installing the Plugin) section of this document again.