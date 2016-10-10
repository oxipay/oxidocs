# The Simple Way (Some HTML/CSS Knowledge)
<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Please note that this documentation is still a work in process
  </div>
</div>

This method decribes the Simple Way to add the banners that are found here. <br> 
For Merchants who are not experienced web developers or do not have access to one, we have created a simple and easy process so that they can display oxipay branding on their websites.
We have provided a series of premade images which have multiple ways that you can display them on your websites.

### Option 1

The easiet way would be to download the image and upload it to the website using the same methods that you uploaded standard content to your site. For example through your text editor in your content management system like Wordpress.
<br>![01-add-media.png](/img/marketing-and-guidlines/01-add-media.png)
<br>Step 1: Add the image through the text editor.
<br>![02-add-link.png](/img/marketing-and-guidlines/02-add-link.png)
<br>Step 2: Make sure you have the image selected and click on the Link option.
<br>![03-add-link.png](/img/marketing-and-guidlines/03-add-link.png)
<br>Step 3: Set it to link to <a target="_blank" href="https://oxipay.com.au/works">https://oxipay.com.au/works</a> and set it to open in a new window.

### Option 2

Alternativly we have provided a small snippit of html that you can use which is found under each image in the for banners section. This will automatically load the images from our servers and display it on your site. It will also include a link to our how it works page so your customers can better undertand how Oxipay will benifit.
The snippit will look something like the following.
```
/** Example HTML **/
<a id="oxipay-banner-01" target="_blank" href="https://oxipay.com.au/works"> <img alt="Oxipay" src="https://images.oxipay.com.au/content/image/oxipay-banner-01" /> </a>
```
#### CSS
There is no CSS styling required if you choose the Simple Way.
However sometime the defualt stylying might not look that great. We recommend that you do apply some basic styling for the best presentation possible.
```
**** Example CSS ****

#oxipay-banner-01 {
    display:block;
    overflow:hidden;
    width:100%;
}
#oxipay-banner-01 img {
    display:block;
    width:100%;
}
```


