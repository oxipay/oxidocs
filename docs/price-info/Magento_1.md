#Adding Magento 1's Price-info Widget
For adding Price-info Widget to your Magento 1 Website, follow the instruction<br>
<strong>Step 1:</strong> Find ```view.phtml``` from the following location in your hosting (Magento installed Folder) and open it with your desired text-editor<br>
```
YOUR_MAGENTO_FOLDER/app/design/frontend/rwd/YOUR_TEMPLATE_FOLDER/template/catalog/product/view.phtml
```
<strong>Step 2:</strong> Find "getPriceHtml"<br>

There should be only one occurance of the "getPriceHtml" string, and it may look similar to:
```
<?php echo $this->getPriceHtml($_product); ?>
```
<strong>Step 3:</strong> Place the following ```<script>``` tag below the "getPriceHtml" code.<br>
```
<script id="EPCarts-price-info" src="https://widgets.%domain%/content/scripts/price-info.js?productPrice=<?php echo $_product->getFinalPrice(); ?>"></script>
```
<div class="alert alert-danger">
    You may try inserting the code a few lines below the "getPriceHtml" code, or below some other elements. Try different places and view the visual appearance to find the most suitable place for your site.<br>
    You may need to flush cache for the changes to take effect. 
</div>
<br>
<strong>Step 4:</strong> Save and you should see a working widget on your website.<br><br>
<script id="EPCarts-price-info" src="https://widgets.%domain%/content/scripts/price-info.js?productPrice=0"></script>
<br>

