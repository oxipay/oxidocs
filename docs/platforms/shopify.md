# Setting up Oxipay on a Shopify Store

This document outlines the steps needed to integrate the Oxipay Payment Gateway into your Shopify store. The Oxipay Payment Gateway enables customers of your store to purchase items using their credit cards on an interest free payment plan.

Please note that Oxipay makes use of Shopify’s API architecture to enable the processing payments via the Oxipay Payment Gateway. This API architecture significantly simplifies the configuration process and eliminates the need to install additional plugins or third party software packages.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Beware of sites or email messages that prompt you to install a plugin or a software package to enable Oxipay as a payment gateway on your Shopify site. Oxipay can be configured without the need for plugins or additional software.
  </div>
</div>

#Integrating Oxipay#

<div class="alert alert-info" role="alert">You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation procdure.</div>

1 – First log into the admin area of your Shopify store, then click on the Settings item at the bottom left.

![1.png](/img/platforms/shopify/1.png)

2 – From the Settings side-bar menu that appears, click on the Payments item. This will open up the Payments options page where you can specify the various payment gateways you would like to enable during checkout.

![2.png](/img/platforms/shopify/2.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Oxipay has been configured as an alternate payment gateway that accepts credit cards. This means that you can continue to use Shopify Payments or PayPal in conjuction with Oxipay. In fact, You can also have other alternative payment gateways such as BitPay running alongside Oxipay.
  </div>
</div>

3 – From within the Alternative Payments section; open up the ‘Select additional payment method’ drop-down menu and select Oxipay.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    The Oxipay option might or might not be visible. If you cannot see Oxipay, proceed to the next step (Step 7). Otherwise, if you can see Oxipay, you can skip to Step 10.
  </div>
</div>

4 – If Oxipay is not visible as an option from the drop-down menu, navigate to the following URL to manually add Oxipay as a payment gateway option:
 
https://www.shopify.com/login?redirect=authorize_gateway%2F1031227

5 – You will be prompted to type in your store address as well as email and password combination.

![3.png](/img/platforms/shopify/3.png)

6 – This will present a screen prompting to add Oxipay as a payment gateway on your store. Click on Add payment gateway.

![4.png](/img/platforms/shopify/4.png)

7 – If successful, you will be presented with a pop-up at the bottom of your screen indicating that Oxipay was successfully added to the Alternative payments section.

![5.png](/img/platforms/shopify/5.png)

8 – Scroll to the Alternative payments section, open up the Select additional payment method drop-down menu and then select Oxipay.

![6.png](/img/platforms/shopify/6.png)

9 – This will open up an area where you can type in your Merchant Number and Encryption Key as provided to you by Certegy, you can also specify the credit cards that you would like to accept on your Shopify store. Then click on Activate.

![7.png](/img/platforms/shopify/7.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Checking the Show checkbox makes your Encryption Key visible as you type it in; otherwise it is hidden and is replaced with a set of dots instead 
  </div>
</div>

10 – This will open up the Oxipay gateway settings area where you can type in your Merchant Number and Encryption Key as supplied to you by Certegy.

Important You will not be able to process payments via Oxipay until you input your Merchant Number and Encryption Key. You will also need to update your Encryption Key if it is recycled via the Merchant Portal.

Below is a description of some of the other settings that might appear on the Oxipay gateway settings area.

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Some of these settings might not be visible to you, such as Test Mode for instance.
  </div>
</div>
 
<table class="table">
  <thead>
    <tr>
      <th>Configuration</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Test Mode</td>
      <td>Ticking this option will run Oxipay in test mode, normally done when troubleshooting or diagnosing issues. In test mode, all Oxipay transactions are simulated and cards are not charged.</td>
    </tr>
    <tr>
      <td>Merchant Number</td>
      <td>This is the unique number that identifies you as a merchant to the Oxipay Payment Gateway.</td>
    </tr>
    <tr>
      <td>Encryption Key</td>
      <td>This is used to authenticate you as a merchant and to ensure that no one can tamper with the information sent as part of purchase orders.</td>
    </tr>
    <tr>
      <td>Cards Accepted</td>
      <td>This is where you can specify that types of Credit Cards you want to accept when customers checkout using Oxipay.</td>
    </tr>
  </tbody>
</table>

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    At the time of writing this document, Oxipay has been configured to only accepts Visa and/or MasterCard credit cards. Please contact us to discuss your options in processing Oxipay transaction using other credit card types.
  </div>
</div>
 
##Oxipay Updates##
Updates to Oxipay might be made in the future to either accommodate newer internet technologies that we deem essential to integrate into our Oxipay Payment Gateway or to accommodate new or deprecated functionality within the Shopify API.
 
If an update is released to Oxipay – such as additional accepted credit card types for instance - and you notice that these changes haven’t been reflected on your Shopify store, we recommend that you de-activate and then re-active Oxipay again. If the issue persists, please contact us to resolve it as soon as possible.
 
<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    De-activating and then re-activating the plugin ensures that your Shopify site detects new configuration changes in the Oxipay Payment Gateway straight away.
  </div>
</div>