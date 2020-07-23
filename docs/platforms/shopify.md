<h1>Setup on Shopify</h1>

To setup and configure Oxipay on your Shopify store, please use the instructions below
<br/>

##Integrating Oxipay##

<div class="panel">
  You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> handy before continuing with the installation.
</div>

1 – Email <a href="mailto:pit@%domain%?Subject=Oxipay URL Request (Shopify)&body=Hi, %0D%0A%0D%0AMy Merchant ID is: %0D%0A%0D%0AI would like to setup Oxipay on my Shopify site. %0D%0A%0D%0AThanks,%0D%0A%0D%0A">pit@%domain%</a> to be sent your unique API key. Please include your Merchant ID in the email.

2 - Add **Oxipay** to your Shopify payments, by following through the link <a href = "https://www.shopify.com/login?redirect=%2Fadmin%2Fauthorize_gateway%2F1052217">here</a>.

3 - Once logged in, you will see the prompt below. Click **Install payment provider**.

![5.png](/img/platforms/shopify/5.png)

4 - If successful, a confirmation message will be display at the bottom of the screen.

![6.png](/img/platforms/shopify/6.png)

5 - Bring the **Alternative Payments** section into focus, expand the **Select additional payment method** drop-down and click **Oxipay - Interest Free Payments**.

<div class="panel">
	To access this page from your Shopify dashboard, select <b>Settings</b> in the bottom left hand corner, then select select <b>Payment providers</b>.
</div>

![7.png](/img/platforms/shopify/7.png)

6 - Enter your **Merchant Number** and **API Key** then click on **Save**. You can also specify the credit cards you want to allow with Oxipay.

![8.png](/img/platforms/shopify/8.png)

<div class="panel">
  The <b>Show</b> checkbox makes your Encryption Key visible as you type it in; otherwise it is masked. 
</div>

<div class="panel">
  Use <b>Test Mode</b> to test Oxipay or diagnose issue; transactions are similated and credit cards are not debited.
</div>

<div class="panel">
  In order to add the Price-info widget as below, please see the Shopify instructions <a href="../../price-info/%no_weekly_shopify%">here</a>.
</div>

<p class="price">
    <span><strong>Product Price</strong>:</span>
    <span id="priceinfo" class="woocommerce-Price-amount amount">
        <span class="woocommerce-Price-currencySymbol">$</span>1400.00
    </span>
</p>
<script class="oxipay-price-info" id="my-id" src="http://widgets.%domain%/content/scripts/payments.js?price-selector=%23priceinfo"></script>
</br>
