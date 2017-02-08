# Adding Shopify's Price-info Widget

For adding Price-info Widget to your Website, follow the instruction<br>
<strong>Step 1:</strong> Login into Shopify backend/Dashboard<br>
<strong>Step 2:</strong> Navigate to Online Store > Themes <br>
![online-store.png](/img/price-info/online-store.png)<br><br>
![thems.png](/img/price-info/theme.png)<br><br>
<strong>Step 3:</strong> From top-right corner, select to Edit HTML/CSS<br>
![theme-editor.png](/img/price-info/theme-editor.png)<br><br>
<strong>Step 4:</strong> From left panel, navigate to Sections and select “product-template.liquid”<br>
![theme-editor.png](/img/price-info/left-sections.png)<br><br>
<strong>Step 5:</strong> Place the ```<script>``` tag in the desired place you'd like it to appear on your website. This should be added before ```Add to Cart ``` button tag.<br>
```
<script id="oxipay-banner" src=" http://images.oxipay.com.au/content/scripts/price-info.js?productPrice={{current_variant.price | divided_by: 100.00}}"></script>
```
<strong>Step 6:</strong> Save and you should see a working widget on your website.
<script id="oxipay-banner" src=" http://images.oxipay.com.au/content/scripts/price-info.js?productPrice={{current_variant.price | divided_by: 100.00}}"></script>

<small>*We reserve to right to change any linked image at anytime without prior notice</small>
<br/><br/>
<small>We strive to write good documentation for our merchants. If there is a way we can improve our documentation, please let us know through <a href="mailto:support@oxipay.com.au?Subject=Oxipay Documentation">support@oxipay.com.au</a></small>
<br>
<br>
<small>Version 1.10</small>
