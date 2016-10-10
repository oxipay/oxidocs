
## The Complex Way (Intimediate HTML/CSS and Javascript Knowledge)

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    Please note that this documentation is still a work in process
  </div>
</div>


If you have some development knowledge or have access to a developer we recommened that you chose this way. 
Choose one or more of the following banners and place the HTML listed in the your prefered spot on your website.
Link to or copy our CSS to your website on the page that the banner will be displayed.
### Linking to Oxipay
If you are more web savy we recommend that you use a modal to open our custom page <a href="https://oxipay.com.au/externalmodal">Exteral Modal</a> in an exteral modal such as Bootstrap 4's Modal.

### Installing the CSS
Download, Intergrate or Link to our external provide CSS.

Option 1
```
<link rel="stylesheet" href="https://images.oxipay.com.au/content/styles/banners.css" type="text/css">
```
Option 2
<br>Download and install our CSS on your website.

<a href="#" download>oxipay-banners.css</a>

Option 3
<br>Install the parts off CSS relivant to the Banners/Tags you are using.
```
@font-face {
    font-family: 'AvenirLTStd-Medium';
    src: url("http://images.oxipay.com.au/Content/fonts/AvenirLTStd-Medium.eot");
    src: local("☺"), url("http://images.oxipay.com.au/Content/fonts/AvenirLTStd-Medium.woff") format("woff"), url("http://images.oxipay.com.au/Content/fonts/AvenirLTStd-Medium.ttf") format("truetype"), url("http://images.oxipay.com.au/Content/fonts/AvenirLTStd-Medium.svg") format("svg");
    font-weight: normal;
    font-style: normal;
}
/** Banner 01 **/

#oxipay-banner-01 {
    width: 100%;
    overflow: hidden;
    display: block;
    max-width: 1120px;
    margin: 0 auto;
    border: 2px solid #e2e2e2;
    max-height: 110px;
    font-family: 'AvenirLTStd-Medium';
    color: #252525;
    text-decoration: none;
}
@media screen and (max-width: 670px) {
    #oxipay-banner-01 {
        margin-top: 20px;
        max-height: 100%;
    }
}
@media screen and (max-width: 750px) {
    #oxipay-banner-01 {
        margin-top: 20px;
    }
}
#oxipay-banner-01 .logo {
    background-color: #252525;
    float: left;
    width: 26%;
    height: 120px;
    padding: 0 2%;
    overflow: hidden;
}
#oxipay-banner-01 .logo img {
    height: 100%;
    max-width: 200px;
    width: 100%;
    margin: 0 auto;
    display: block;
}
#oxipay-banner-01 .text {
    float: left;
    padding-left: 2%;
    padding-top: 10px;
    overflow: hidden;
    width: 54%;
}
#oxipay-banner-01 h3 {
    font-size: 30px;
    margin: 0;
    font-family: 'AvenirLTStd-Medium';
    color: #252525;
}
#oxipay-banner-01 p {
    font-size: 16px;
    margin: 0;
}
#oxipay-banner-01 .button {
    width: 20%;
    overflow: hidden;
    float: left;
}
#oxipay-banner-01 .info {
    display: block;
    float: right;
    line-height: 30px;
    padding: 10px 15px;
    background-color: #e68821;
    margin-right: 15px;
    margin-top: 30px;
    color: white;
    border-radius: 2px;
}
#oxipay-banner-01:hover .info {
    background-color: #bf6e15;
}
@media screen and (max-width: 670px) {
    #oxipay-banner-01 .logo {
        width: 100%;
        float: none;
    }
    #oxipay-banner-01 .text {
        width: 100%;
        float: none;
    }
    #oxipay-banner-01 .button {
        width: 100%;
        float: none;
        margin-top: 10px;
    }
    #oxipay-banner-01 .info {
        margin: 0 auto;
        float: right;
        margin: 0 15px 15px;
    }
}

/** Tag 01 **/
#oxipay-tag-01 {
    width: 100%;
    background: #252525;
    color: white;
    margin-top: 20px;
    padding: 10px;
    display: block;
    overflow: hidden;
}
#oxipay-tag-01 img {
    height: 20px;
    margin-bottom: -6px;
}
#oxipay-tag-01 span {
    float: right;
    color: white;
}

```
