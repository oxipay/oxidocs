
# The Developer Way
(Intermediate HTML/CSS and JQuery Knowledge)
This method describes the recommened way to add Oxipay banners and tags to your website. Which can be found here <a href="/guidelines/banners">here.</a>

## Installing the CSS
To use our custom CSS please add the following link to your ```<head>``` tag in you sites HTML.
```
<link rel="stylesheet" href="//images.oxipay.com.au/content/styles/oxipay-branding.css" type="text/css">
```
##Installing the Banners and Tags
<strong>Step 1:</strong> Choose the Banner or Tag that you want to install from our list <a href="/guidelines/banners">here</a>. 
<br><strong>Step 2:</strong> Place the HTML snippet in the desired place you'd like it to appear on your website. Depending on how your website is made this may vary.
<br><br>Shopify uses can find their HTML by logging into your admin panel and clicking Online Store > Themes > Click on the "..." > Then Edit HTML/CSS
We recommened placing the Banner in your base layout html so it will appear on all the pages in your website and placing the tag under the price variable on your products single page. 
<br><br><strong>Step 3:</strong> Save and if you have installed the CSS correctly you should see a working Banner or Tag on the pages you edited on your website. If they are not displaying correctly please check to see if the CSS is being loaded.
<br><strong>Step 4:</strong> Install one of the below Modals.

## Installing the Modal Page


When a user clicks on the banner rather than open the link in a new page, we recommend having a modal appear that explains the benefits of our service.
In this page we will explain two methods to achieving this and a third for users who want to display it in their own custom modal.


**Desired outcome:**

<a href="#oxipay-modal" id="#oxipay" rel="modal:open" class="btn btn-primary" data-toggle="modal" data-target="#oxipay-modal">
  Launch demo modal
</a>

###Option 1 - JQuery Modal:
Our modal of choice is called JQuery Modal and this option is written to work with it.
<br><strong>Step 1:</strong> Install JQuery Modal by following the instructions in here <a href="https://github.com/kylefox/jquery-modal">JQuery Modal Installation Guide</a>.
<br><strong>Step 2:</strong> After you have installed JQuery Modal copy the below HTML into your websites HTML on the pages you would like it to be used. We recommend adding to your websites main layout page just before the closing ```</body>``` tag.
<br><strong>Step 3:</strong> Click on either the Banner or Tag you installed. You should get a similar result to the above example. 
<br><br>**Jquery Modal HTML**
```
 <div id="oxipay-modal" style="display:none;">
    <iframe id="oxipay-external" src="https://oxipay.com.au/externalmodal"></iframe>
  </div>
```
###Option 2 - Bootstrap Modal: 
For websites that have Bootstrap installed this is the recommened option.
<br><strong>Step 1:</strong> Copy the below HTML into your sites HTML on the pages you would like it to be used. We recommened adding to your websites main layout page just before the closing ```</body>``` tag.
<br><strong>Step 2:</strong> Click on either the Banner or Tag you installed. You should get a similar result to the above example. 
<br><br>**Bootstrap Modal HTML**
```
<div class="modal fade" id="oxipay-modal" tabindex="-1" role="dialog">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <iframe id="oxipay-external" src="https://oxipay.com.au/externalmodal"></iframe>
      <div class="modal-footer">
        <button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
```

###Option 3 - Custom Modal
If you are using your own custom modal please place the following code inside of it
```
<iframe id="oxipay-modal" src="https://oxipay.com.au/externalmodal"></iframe>
```
<link rel="stylesheet" href="//images.oxipay.com.au/content/styles/oxipay-branding.css" type="text/css">
<div id="oxipay-modal" style="display:none;">
<iframe id="oxipay-external" src="https://oxipay.com.au/externalmodal/index"></iframe>
</div>