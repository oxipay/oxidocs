
# The Complex Way
(Intermediate HTML/CSS and JQuery Knowledge)
This method describes the Complex Way to add the banners that are found <a href="/guidelines/banners">here.</a>

If you have some development knowledge or have access to a developer we recommend that you choose this way. 
Choose one or more of the following banners and place the HTML listed in the your preferred spot on your website.
Link to or copy our CSS to your website on the page that the banner will be displayed.

## Installing the CSS
To use our custom CSS please add the following link to your ```<head>``` tag in you sites HTML.
```
<link rel="stylesheet" href="//images.oxipay.com.au/content/styles/oxipay-branding.css" type="text/css">
```
##Installing the Banners and Tags
Choose the banners or tag that you want to install from our list <a href="/guidelines/banners">here</a> and grab the Complex Way HTML. Place that in the HTML of your website in the desired location that you would like it to appear. If you have the CSS installed then the banner should display correctly.

## Installing the Modal Page


When a user clicks on the banner rather than open the link in a new page, we recommend having a modal appear that explains the benefits of our service.
In this page we will explain two methods to achieving this and a third for users who want to display it in their own custom modal.


**Desired outcome:**


<a href="#oxipay-modal" id="#oxipay" rel="modal:open" class="btn btn-primary" data-toggle="modal" data-target="#oxipay-modal">
  Launch demo modal
</a>

###Option 1 - JQuery Modal:
Our modal of choice is called JQuery Modal and this option is written to work with it.
To install JQuery Modal please follow the instruction laid out in here <a href="https://github.com/kylefox/jquery-modal">JQuery Modal Installation Guide</a>.

After you have installed JQuery Modal copy the below HTML into your websites HTML on the pages you would like it to be used. We recommend adding to your websites main layout page just before the closing ```</body>``` tag.
<br><br>**Jquery Modal HTML**
```
 <div id="oxipay-modal" style="display:none;">
    <iframe id="oxipay-external" src="https://oxipay.com.au/externalmodal"></iframe>
  </div>
```
###Option 2 - Bootstrap Modal: 
If you have Bootstrap installed on your website than this is the option you should choose.
All oyu need to do is copy the below HTML into your sites HTML on the pages you would like it to be used. We recommened adding to your websites main layout page just before the closing ```</body>``` tag.
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