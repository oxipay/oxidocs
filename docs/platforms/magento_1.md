# Setting up Oxipay on a Magento 1 Store

This document outlines the steps needed to integrate the Oxipay Payment Gateway into your Magento store.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    At the time of writing this article; Oxipay was developed and tested using Magento Community Edition 1.9. Issues might be encountered if using a different version. If you do encounter issues, please contact us to resolve them as soon as possible.
  </div>
</div>
<br/>

## Installing the Plugin

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    You will need your <b>Merchant ID</b> and a corresponding <b>Encryption Key</b> before continuing with the installation. If you don't have either of these bits of information; please contact <a href="mailto:support@oxipay.com.au?Subject=Merchant ID">support@oxipay.com.au</a>.
  </div>
</div>

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Performing the steps below requires some knowledge of the Magento platform. We recommend that these steps be performed by an IT professional or a web developer.<br/><br/>
    Before proceeding with the rest of the installation; ensure that you have a back of your Magento store. To create a backup, navigate to System -> Tools -> Backup. This is useful in the event you encounter issues with installing Oxipay.
  </div>
</div>

1 - You can install the Oxipay plugin manually by copying the [oxipay-magento-1.x](https://github.com/oxipay/oxipay-magento-1.x) source code into the <code>/app</code> folder under the Magento root directory. A zip file containing the Oxipay plugin can be found at the following location:<br/>
[https://github.com/oxipay/oxipay-magento-1.x/releases](https://github.com/oxipay/oxipay-magento-1.x/releases)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    oxipay-magento-1.x is a private GitHub repository. If you don't have access, please contact <a href="mailto:support@oxipay.com.au?Subject=Merchant ID">support@oxipay.com.au</a> to get access or to receive the plugin via email.
  </div>
</div>

2 - Copy the unzipped files to the <code>/app</code> folder under the Magento root directory.

3 - Login into the Magento **Admin Panel**. then click on **System** > **Cache Management**.

![1.png](/img/platforms/magento_1/1.png)

![2.png](/img/platforms/magento_1/2.png)

4 - From within the **Cache Management** page; click on the **Flush Magento Cache** button.

![3.png](/img/platforms/magento_1/3.png)

5 - Confirm that Oxipay has been installed on your Magento Store. To do this, click on **System** > **Configuration**.

![4.png](/img/platforms/magento_1/4.png)

6 - This will open up the **Configuration** page, scroll to the bottom and then click on **Payment Methods** on the left side menu.

![5.png](/img/platforms/magento_1/5.png)

7 - Confirm that Oxipay Checkout is visible as a Payment Method and once expanded it looks similar to the image below.

![6.png](/img/platforms/magento_1/6.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    The <b>Merchant Key</b> and <b>API Key</b> have been blacked out in the image above.
  </div>
</div>
<br/>

##Updates to Oxipay##

Updates to the Oxipay plugin might be made in the future. To update the Oxipay plugin, we recommend that you first uninstall the existing Oxipay plugin before installing a newer version.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Deleting the existing plugin ensures that any files from the previous version don't cause any issues with the newer version.
  </div>
</div>

1 - Open the <code>app</code> folder under the Magento root folder. Delete the files and folder paths listed below:

<b>Folders</b>:

* <code>app\code\community\Oxipay</code>
* <code>app\design\frontend\base\default\template\oxipayments</code>

<b>Files</b>:

* <code>app\etc\modules\Oxipay_Oxipayments.xml</code>

2 - Login to **Magento Admin** and then navigate to **System** > **Cache Management**.

![2.png](/img/platforms/magento_1/2.png)

3 - On the top right, click on Flush Cache Storage to clear Magento's cache.

![3.png](/img/platforms/magento_1/3.png)

4 - Now you can proceed with installing the new version of the Oxipay plugin by following the [Installing the Plugin](#installing-the-plugin) section.
