# Introduction

This section is a Developer's guide into how to integrate Oxipay into shopping carts that allow integration of external payment gateways. We have already used this API to integrate Oxipay as a payment method into a number of leading shopping carts and eCommerce solutions including Shopify, WooCommerce and Magento.

<div class="panel panel-primary">
  <div class="panel-heading">
    <h3 class="panel-title">Note</h3>
  </div>
  <div class="panel-body">
    This guide assumes that the Developer has prior knowledge and familiarity with the shopping cart they intend to integrate Oxipay into.
  </div>
</div>

Shopping carts vary in the way they process a purchase order including in what they classify as mandotary information needed to process a transaction, they way the communicate a purchase order over the internet and the way the process it.

To accomodate these differences between the variou shopping platforms and to reduce the amount code changes that have to be introduced to the underlying Oxipay code, a generic translation layer has been developed.

To integrate Oxipay into your choice of shopping carts, you will need to massage the purchase payload information from a format that is specific to that particular shopping platform into a format that can be read and processed by the translation layer. Upon successfully processing the transation payload, the translation layer would then pass the purchase order to Oxipay for further processing.
