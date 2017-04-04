#Adding WooCommerce's Price-info Widget
For adding Price-info Widget to your Website, follow the instruction<br>
<strong>Step 1:</strong> Find ```Price.php``` from the following location in your hosting (Wordpress installed Folder) and open it with your desired text-editor <br>
```
YourWordpressFolder\wp-content\plugins\woocommerce\templates\single-product
```
<strong>Step 2:</strong> Find "Price tag" as shown below <br>
```
<p class="price"><?php echo $product->get_price_html(); ?></p>
```
<strong>Step 3:</strong> Place the ```<script>``` tag in the below "Price tag".<br>
```
<script id="oxipay-banner" src="https://widgets.oxipay.com.au/content/scripts/price-info.js?productPrice=<?php echo $product->get_display_price() ?>"></script>
```
<strong>Step 4:</strong> Save and you should see a working widget on your website.<br><br>
<script id="oxipay-banner" src="https://widgets.oxipay.com.au/content/scripts/price-info.js?productPrice=0"></script>
<br>
<div class="alert alert-danger">
  <strong>Note:</strong> If you are using a custom template for WooCommerce, "Price.php" will be located in "yourtheme/woocommerce/single-product/price.php."
</div>
<br>

<small>**We reserve the right to change any linked image at anytime without prior notice</small>
<br/><br/>
<small>We strive to write good documentation for our merchants. If there is a way we can improve our documentation, please let us know through <a href="mailto:support@oxipay.com.au?Subject=Oxipay Documentation">support@oxipay.com.au</a></small>
<br>
<br>
<small>Version 1.10</small>
