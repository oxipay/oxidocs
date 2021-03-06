### More-info large
**(fortnightly repayments)**
<script id="moreInfoLarge" src="https://widgets.%domain%/content/scripts/more-info-large.js"></script>
```
<script id="oxipay-banner" src="https://widgets.%domain%/content/scripts/more-info-large.js"></script>
```
**(weekly repayments)**
<script id="moreInfoLarge" src="https://widgets.%domain%/content/scripts/more-info-large.js?weekly"></script>
```
<script id="oxipay-banner" src="https://widgets.%domain%/content/scripts/more-info-large.js?weekly"></script>
```
<br/>

### More-info small
**(fortnightly repayments)**
<script id="moreInfoSmall" src="https://widgets.%domain%/content/scripts/more-info-small.js"></script>
```
<script id="oxipay-banner" src="https://widgets.%domain%/content/scripts/more-info-small.js"></script>
```
**(weekly repayments)**
<script id="moreInfoSmall" src="https://widgets.%domain%/content/scripts/more-info-small.js?weekly"></script>
```
<script id="oxipay-banner" src="https://widgets.%domain%/content/scripts/more-info-small.js?weekly"></script>
```
<br>

### Price-info widget

**(fortnightly repayments)**
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/payments.js?productPrice=100"></script>
```
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/payments.js?productPrice=PLACE_YOUR_PRODUCT_PRICE"></script>
```

**(weekly repayments)**
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/payments-weekly.js?productPrice=100"></script>
```
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/payments-weekly.js?productPrice=PLACE_YOUR_PRODUCT_PRICE"></script>
```
(Please note that weekly price-info widget will be hidden when the product price is < $40)
<br>

### Dynamic Price-info widget

For instances where you have multiple products on the same page, or the price of the product dynamically updates as a result of user selection; we provide a more sophisticated price-info widget. 

With this widget you can provide a **URL encoded** jquery style CSS selector and it will bind a call back to the DOMSubTreeModified event. If the price is modified, it will update the payment info accordingly. 

For example, this is a block of html extracted from a typical woo-commerce product page. 

```
    <span>Product Price:</span>
    <p class="price">
        <span id="priceinfo" class="woocommerce-Price-amount amount">
            <span class="woocommerce-Price-currencySymbol">$</span>1400.00
        </span>
    </p>
```

In this case we use the urlencoded ```%23priceinfo ``` to refer to the id ```#priceinfo```

**(fortnightly repayments)**
<p class="price">
    <span><strong>Product Price</strong>:</span>
    <span id="priceinfo" class="woocommerce-Price-amount amount">
        <span class="woocommerce-Price-currencySymbol">$</span>1400.00
    </span>
</p>
<script class="oxipay-price-info" id="my-id" src="https://widgets.%domain%/content/scripts/payments.js?price-selector=%23priceinfo"></script>
```
<script class="oxipay-price-info" id="my-id" src="https://widgets.%domain%/content/scripts/payments.js?price-selector=%23priceinfo"></script>
```
<br>
**(weekly repayments)**
<p class="price">
    <span><strong>Product Price</strong>:</span>
    <span id="priceinfo2" class="woocommerce-Price-amount amount">
        <span class="woocommerce-Price-currencySymbol">$</span>1400.00
    </span>
</p>
<script class="oxipay-price-info" id="my-id" src="https://widgets.%domain%/content/scripts/payments-weekly.js?price-selector=%23priceinfo2"></script>
```
<script class="oxipay-price-info" id="my-id" src="https://widgets.%domain%/content/scripts/payments-weekly.js?price-selector=%23priceinfo2"></script>
```
<br>
You could also use ```price-selector=.woocommerce-Price-amount.amount``` if your product price isn't accessible by an xml:id 

If you *do not* provide a ```price-selector``` query argument then you can also use a fixed  ```productPrice``` value. In this instance, the payment period will not update if the price is updated.

### Minimum and Maximum Price-info widget (Optional)

To alter the Price-info widget based on the price passed to it, you may set the minimum and maximum values it will display for.

This is done by setting the ```data-min``` and ```data-max``` fields when calling the Price-info widget script as seen below.
```
<script data-min="20" data-max="300" src="https://widgets.%domain%/content/scripts/payments-weekly.js?productPrice=YOUR_PRICE"></script>
```
In this instance the Price-info widget will not display if the proudct price is above $300 and will display in an altered form if the value is below $20 as seen below.

<script data-min="20" data-max="300" src="https://widgets.%domain%/content/scripts/payments.js?productPrice=0"></script>
<br>
By default the **Price-info** widget will not display for prices above $%max_purchase%.
<br>
By default the **Price-info weekly** widget will not display for prices above $%max_purchase% and below 40.
<br/>

### Oxipay Deposit Increase

As of **19/03/2020** the initial deposit for weekly repayments was changed to **25% of the purchase price**.
In the case that you have created a custom widget on your website, you will need to alter the calculation logic to reflect this change.

The first repayment will always be **25%** of the Oxipay purchase amount, and the remaining amount will be split into **7 equal weekly repayments**.

The below Javascript code is an example of the change in calculation:
```
    productPrice = 781.90
    let initialDeposit = Math.floor((productPrice / 4) * Math.pow(10, 2)) / Math.pow(10, 2);
    let remainingWeeklyRepayment = (productPrice - initialDeposit) / 7;

    let roundedDownWeeklyRepayment = Math.floor(remainingWeeklyRepayment * Math.pow(10, 2)) / Math.pow(10, 2)

    <a id="oxipay">
      <p>or 1 initial payment of <b>$${initialDeposit.toFixed(2)}</b></p>
      <p>and 7 weekly payments of <b>$${roundedDownWeeklyRepayment.toFixed(2)}</b></p>
      <p>Interest free with <span id="oxipay-img"></span><span class="more-info">more info</span></p>
    </a>
```
If you have any questions, or need assistance, please contact us at <a href = "mailto:pit@shophumm.co.nz">pit@shophumm.co.nz</a>

<br>

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Installation based on Platforms</h3>
  </div>
  <div class="panel-body">
<ul>
  <li><a href="../../price-info/shopify">Shopify specific instructions</a></li>
  <li><a href="../../price-info/woocommerce">WooCommerce specific instructions</a></li>
</ul>
  </div>
</div>

<br/><br/>

<small>*We reserve the right to change any linked image at anytime without prior notice</small>
<br/><br/>
<small>We strive to write good documentation for our merchants. If there is a way we can improve our documentation, please let us know through <a href="mailto:support@%domain%?Subject=Oxipay Documentation">support@%domain%</a></small>
<br>
<br>
<small>Version 1.10</small>
