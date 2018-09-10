---
title: ""
menuTitle: "WooCommerce"
date: 2018-05-17T12:13:55+09:30
draft: false
---

<h1>Setup on WooCommerce</h1>

<div class="panel">
  You will need your <b>Merchant ID</b> and an <b>Encryption Key</b> for the installation.
</div>

1 - Log into the WordPress admin area, then click on **Plugins** on the sidebar.

![1.png](/img/platforms/woocommerce/1.png)

2 - Click on **Add New** on the top left.

![2.png](/img/platforms/woocommerce/2.png)

3 - In the top left, type Oxipay in the **Search plugins...** search box then hit Enter.

![3.png](/img/platforms/woocommerce/3.png)

4 - From the search results, click on **Install Now** next to **Oxipay Payment Gateway for WooCommerce**.

![29.png](/img/platforms/woocommerce/29.png)

5 - Still on the same page and once installation is successful, you should see the **Activate** button. Click on it.

![30.png](/img/platforms/woocommerce/30.png)

6 - This will re-direct you to **Plugins** page, confirm that Oxipay is installed and activated.

![31.png](/img/platforms/woocommerce/31.png)

## Configuring Plugin

1 - From the side-bar, click on **WooCommerce** then on **Settings**.

![32.png](/img/platforms/woocommerce/32.png)

2 - From the top bar, click on **Checkout** then on **Oxipay**.

![33.png](/img/platforms/woocommerce/33.png)


Below is a screenshot of the various Oxipay settings available and what they are for.

![34.png](/img/platforms/woocommerce/34.png)

**Enabled**: Enables or disables Oxipay

**Price Widget**: Displays an Oxipay price widget on each of your store's product pages. (**Recommended**)

**Shop Name**: Your store name that will be displayed in WooCommerce email receipts to customers

**Oxipay Region**: Region where your store is located as per your merchant agreement.

**Test Mode**: For troubleshooting of issues or testing of Oxipay's user experience.

**Modal Checkout**: Completes transaction on your store for a more seamless experience.

**Merchant ID**: Provided to you as part of your welcome pack.

**API Key**: Provided to you by Platform Integration Team; used to verify orders from your store.

**Minimum Order Total**: Orders below that will not have Oxipay as a payment option.

**Maximum Order Total**: Orders above that will not have Oxipay as a payment option.

<div class="panel">
  Leaving both - Minimum and Maximum Order Totals - blank will enable Oxipay on all products.
</div>
