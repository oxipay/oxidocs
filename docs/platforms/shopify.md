#Setting up OxiPay on your Shopify Store#
This document outlines the steps needed to integrate the OxiPay Payment Gateway into your Shopify store. The OxiPay Payment Gateway enables customers of your store to purchase items using their credit cards on an interest free payment plan.

Please note that Oxipay makes use of Shopify’s API architecture to enable the processing payments via the OxiPay Payment Gateway. This API architecture significantly simplifies the configuration process and eliminates the need to install additional plugins or third party software packages.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Beware of sites or email messages that prompt you to install a plugin or a software package to enable OxiPay as a payment gateway on your Shopify site. OxiPay can be configured without the need for plugins or additional software.
  </div>
</div>

#Integrating OxiPay#
1 – First log into the admin area of your Shopify store, then click on the Settings item at the bottom left.

2 – From the Settings side-bar menu that appears, click on the Payments item. This will open up the Payments options page where you can specify the various payment gateways you would like to enable during checkout.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Oxipay has been configured as an alternate payment gateway that accepts credit cards. This means that you can continue to use Shopify Payments or PayPal in conjuction with Oxipay. In fact, You can also have other alternative payment gateways such as BitPay running alongside Oxipay.
  </div>
</div>

6 – From within the Alternative Payments section; open up the ‘Select additional payment method’ drop-down menu and select OxiPay.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    The OxiPay option might or might not be visible. If you cannot see Oxipay, proceed to the next step (Step 7). Otherwise, if you can see Oxipay, you can skip to Step 10.
  </div>
</div>

7 – If Oxipay is not visible as an option from the drop-down menu, navigate to the following URL to manually add Oxipay as a payment gateway option:
 
https://www.shopify.com/login?redirect=authorize_gateway%2F1031227

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Copy and paste the above URL in a new tab in the current browser window that you are using. Clicking on the link might open it up in a different browser depending on how you setup your default computer browsers.
  </div>
</div>

8 – You will be prompted to type in your store address as well as email and password combination.

8 – This will present a screen prompting to add Oxipay as a payment gateway on your store. Click on Add payment gateway.

9 – If successful, you will be presented with a pop-up at the bottom of your screen indicating that Oxipay was successfully added to the Alternative payments section.

10 – Scroll to the Alternative payments section, open up the Select additional payment method drop-down menu and then select Oxipay.

11 – This will open up an area where you can type in your Merchant Number and Encryption Key as provided to you by Certegy, you can also specify the credit cards that you would like to accept on your Shopify store. Then click on Activate.


<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Checking the Show checkbox makes your Encryption Key visible as you type it in; otherwise it is hidden and is replaced with a set of dots instead 
  </div>
</div>

9 – This will open up the Oxipay gateway settings area where you can type in your Merchant Number and Encryption Key as supplied to you by Certegy.

Important You will not be able to process payments via Oxipay until you input your Merchant Number and Encryption Key. You will also need to update your Encryption Key if it is recycled via the Merchant Portal.

8 – Below is a description of some of the other settings that might appear on the Oxipay gateway settings area.

<div class="panel panel-danger">
  <div class="panel-heading">
    <h3 class="panel-title">Important</h3>
  </div>
  <div class="panel-body">
    Some of these settings might not be visible to you, such as Test Mode for instance.
  </div>
</div>
 

**Test Mode**: Ticking this option will run Oxipay in test mode, normally done when troubleshooting or diagnosing issues. In test mode, all Oxipay transactions are simulated and cards are not charged.

**Merchant Number**: This is the unique number that identifies you as a merchant to the OxiPay Payment Gateway.

**Encryption Key**: This is used to authenticate you as a merchant and to ensure that no one can tamper with the information sent as part of purchase orders.

**Cards Accepted**: This is where you can specify that types of Credit Cards you want to accept when customers checkout using OxiPay.
 

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    At the time of writing this document, OxiPay has been configured to only accepts Visa and/or MasterCard credit cards. Please contact us to discuss your options in processing OxiPay transaction using other credit card types.
  </div>
</div>
 
##OxiPay Updates##
Updates to OxiPay might be made in the future to either accommodate newer internet technologies that we deem essential to integrate into our OxiPay Payment Gateway or to accommodate new or deprecated functionality within the Shopify API.
 
If an update is released to OxiPay – such as additional accepted credit card types for instance - and you notice that these changes haven’t been reflected on your Shopify store, we recommend that you de-activate and then re-active OxiPay again. If the issue persists, please contact us to resolve it as soon as possible.
 
<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    De-activating and then re-activating the plugin ensures that your Shopify site detects new configuration changes in the OxiPay Payment Gateway straight away.
  </div>
</div>