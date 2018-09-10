---
title: ""
menuTitle: "Price-info Widget for WooCommerce"
date: 2018-05-17T12:13:55+09:30
draft: true
---

#Adding WooCommerce's Price-info Widget
For adding Price-info Widget to your Website, follow the instruction<br>
<strong>Step 1:</strong> Find ```price.php``` from the following location in your hosting (Wordpress installed Folder) and open it with your desired text-editor <br>
```
YourWordpressFolder\wp-content\plugins\woocommerce\templates\single-product
```
<strong>Step 2:</strong> Find "Price tag" as shown below <br>
```
<p class="price"><?php echo $product->get_price_html(); ?></p>
```
<strong>Step 3:</strong> Place the following ```<script>``` tag below the "Price tag".<br>
```
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/price-info.js?productPrice=<?php echo wc_get_price_to_display($product); ?>"></script>
```
<strong>Step 4:</strong> Save and you should see a working widget on your website.<br><br>
<script id="oxipay-price-info" src="https://widgets.%domain%/content/scripts/price-info.js?productPrice=0"></script>
<br>
<div class="alert alert-danger">
  <strong>Note:</strong> If you are using a custom template for WooCommerce, "price.php" will be located in "yourtheme/woocommerce/single-product/price.php."
</div>
<br>

