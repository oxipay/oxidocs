# The Simple Way
(Some HTML/CSS Knowledge)
This method describes the Simple Way to add the banners that are found <a href="/guidelines/banners">here.</a>
<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Please note that this documentation is still a work in progress
  </div>
</div>
For Merchants who are not experienced web developers or do not have access to one, we have created a simple and easy process so that they can display oxipay branding on their websites.
We have provided a series of premade images which have multiple ways that you can display them on your websites.

### Option 1

Download the desired banner or tag from our <a href="/guidelines/banners">banners section</a>. Log into your websites Content Managment System (eg: Wordpress) and click on edit to the page that you would like the banner to appear on. Then follow the steps below.
<br>Step 1: Add the image through the text editor.
<br>![01-add-media.png](/img/marketing-and-guidlines/01-add-media.png)
<br>Step 2: Make sure you have the image selected and click on the Insert link option.
<br>![02-add-link.png](/img/marketing-and-guidlines/02-add-link.png)
<br>Step 3: Set it to link to <a target="_blank" href="https://oxipay.com.au/works">https://oxipay.com.au/works</a> and to open in a new window.
<br>![03-add-link.png](/img/marketing-and-guidlines/03-add-link.png)

### Option 2

Alternatively we have provided a small snippet of html that you can use. This is found under each image in the <a href="/guidelines/banners">banners section</a>. This will automatically load the images from our servers and display it on your site. It will also include a link to our "how it works" page so your customers can better understand how Oxipay will benefit.
The snippet will look something like the following.
```
/** Example HTML **/
<a id="oxipay-banner-01" target="_blank" href="https://oxipay.com.au/works"><img src="//images.oxipay.com.au/content/images/oxipay-banner-01.png"></a>
```
#### CSS
There is no CSS styling required if you choose the Simple Way.
However sometime the default styling might not be enough. We recommend that you do apply some basic styling for the best presentation possible.
```
**** Example CSS ****

#name-of-banner {
    display:block;
    overflow:hidden;
    width:100%;
}
#name-of-banner img {
    display:block;
    width:100%;
}
```


