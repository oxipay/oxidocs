# Setting up Oxipay on a Magento 2 Store

This document outlines the steps needed to integrate the Oxipay Payment Gateway into your Magento v2 store.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    At the time of writing this article, Oxipay was developed and tested using Magento Community Edition v2.1.2 <br/>
    Issues might be encountered if using an earlier version or a later version. If you do encounter issues, then please contact us to resolve them as soon as possible.
  </div>
</div>

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Please consult the Magento v1 documentation if planning on integrating Oxipay into a Magento v1 Community Edition.
  </div>
</div>

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

4 - Login into the Magento **Admin Panel**, then from the left side menu, click on **System**.

![1.png](/img/platforms/magento_2x/1.png)

5 - This will open up the **System** submenu. Click on **Cache Management**.

![2.png](/img/platforms/magento_2x/2.png)

6 - From within the **Cache Management** page, click on the **Flush Magento Cache** button in the top right.

![3.png](/img/platforms/magento_2x/3.png)

7 - Confirm that Oxipay has been installed on your Magento Store. To do this, click on **System** in the **Admin Panel** then on **Configuration**.

![4.png](/img/platforms/magento_1x/4.png)

8 - This will open up the **Configuration** page, scroll to the bottom and then click on **Payment Methods** on the left side menu.

![5.png](/img/platforms/magento_1x/5.png)

9 - Confirm that Oxipay Checkout is visible as a Payment Method and once expanded it looks similar to the image below.

![6.png](/img/platforms/magento_1x/6.png)

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