# Setting up Oxipay on a Shopify Store

This document outlines the steps needed to integrate the Oxipay Payment Gateway into your Shopify store. The Oxipay Payment Gateway enables customers of your store to purchase items using their credit cards on an interest free payment plan.
<br/>

#Integrating Oxipay#

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    You will need your <b>Merchant ID</b> and a corresponding <b>Encryption Key</b> before continuing with the installation. If you don't have either of these bits of information; please contact <a href="mailto:support@oxipay.com.au?Subject=Merchant ID">support@oxipay.com.au</a>.
  </div>
</div>

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

![3.png](/img/platforms/shopify/3.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    The Oxipay option might or might not be visible. If you cannot see Oxipay, proceed to the next step. Otherwise, if you can see Oxipay, you can skip to Step 8.
  </div>
</div>

4 – If Oxipay is not visible as a payment option from the drop-down menu, please contact <a href="mailto:support@oxipay.com.au?Subject=Gateway Authorisation">support@oxipay.com.au</a> to request gateway authorisation. You should get a response within 1-2 business days containing a link that will enable Oxipay as a payment gateway option within your web-store:

5 – Once you click on the link; you will be prompted to type in your store address as well as your email-address/username and password as shown below:

![4.png](/img/platforms/shopify/4.png)

6 – Once you've Logged in; You will be presented with a screen prompting to add Oxipay as a payment gateway. Click on Add payment gateway.

![5.png](/img/platforms/shopify/5.png)

7 – If successful, you will be presented with a pop-up at the bottom of your screen indicating that Oxipay was successfully added to the Alternative payments section.

![6.png](/img/platforms/shopify/6.png)

8 – Scroll to the Alternative payments section, open up the Select additional payment method drop-down menu and then select Oxipay.

![7.png](/img/platforms/shopify/7.png)

9 – This will open up an area where you can type in your Merchant Number and Encryption Key as provided to you by Certegy, you can also specify the credit cards that you would like to accept on your Shopify store. Then click on Activate.

![8.png](/img/platforms/shopify/8.png)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Checking the Show checkbox makes your Encryption Key visible as you type it in; otherwise it is hidden and is replaced with a set of dots instead 
  </div>
</div>

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    You will not be able to process payments via Oxipay until you input your Merchant Number and Encryption Key. You will also need to update your Encryption Key if it is recycled via the Merchant Portal.
  </div>
</div>

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
<br/>
 
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
