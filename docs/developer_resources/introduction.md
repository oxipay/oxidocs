# Introduction

This section provides information on how a developer can go about integrating Oxipay into a shopping cart that allows integration with an external paymnet gateway. We have successfully used this API ourselves to ingrate Oxipay as a payment option into a number of leading shopping carts and eCommerce solutions including Shopify, WooCommerce and Magento.

Shopping carts vary in the way they deal with transaction information, the way they communicate such information as well as they way the classify certain information as optional or mandatory. To deal with this, Oxipay implements an API that is intended to work with as many shopping carts as possible. In this guide, you will find information as to what sort of information is needed for us to be able to process a transaction via Oxipay and also the format we expect this information to be in.

You will also find information on how to go about singing your request in order to protect against malicious attacks as well as session hijacking.

**NOTE** This guide assumes prior knowledge and familiarity with the shopping cart that Oxipay is to be integrated into. We understand that shopping carts vary in the way they are designed - Saas (Shopify) vs Plugin architecture (WooCommerce). You should still be able to integrate Oxipay into your choice of shopping cart regardless of these changes.