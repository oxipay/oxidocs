---
title: "Price-info Widget for Shopify"
menuTitle: "Price-info Widget for Shopify"
date: 2018-05-17T12:13:55+09:30
draft: false
weight: 2
---


For adding Price-info Widget to your Website, follow the instruction<br>
<strong>Step 1:</strong> Login into Shopify backend/Dashboard<br>
<strong>Step 2:</strong> Navigate to Online Store > Themes <br>
![online-store.png](/images/price-info/online-store.png)<br><br>
![theme.png](/images/price-info/theme.png)<br><br>
<strong>Step 3:</strong> From top-right corner, select to Edit HTML/CSS<br>
![theme-editor.png](/images/price-info/theme-editor.png)<br><br>
<strong>Step 4:</strong> From left panel, navigate to "Sections" and select "product-template.liquid"<br>
![theme-editor.png](/images/price-info/left-sections.png)<br><br>
<div class="panel">
    <b>If the "product-template.liquid" file does not exist</b>, navigate to "Templates" and select "product.liquid" instead.
</div>
<strong>Step 5:</strong> Place the ```<script>``` tag in the desired place you'd like it to appear on your website. This should be added before ```Add to Cart ``` button tag.<br>

**(fortnightly repayments)**
```
<script id="oxipay-price-info" src="https://widgets.{{< domain >}}/content/scripts/payments.js?productPrice={{product.selected_or_first_available_variant.price | divided_by: 100.00}}"></script>
```
**(weekly repayments)**
```
<script id="oxipay-price-info" src="https://widgets.{{< domain >}}/content/scripts/payments-weekly.js?productPrice={{product.selected_or_first_available_variant.price | divided_by: 100.00}}"></script>
```

<strong>Step 6:</strong> Save and you should see a working widget on your website.<br><br>

