# Introduction

This section provides information on how a developer can go about integrating EPCarts into a shopping cart that allows for external payment gateways. We have successfully used this API ourselves to integrate EPCarts as a payment option into a number of leading shopping cart platforms and eCommerce solutions including Shopify, WooCommerce and Magento.

Shopping carts vary in the way they deal with transaction information, the way they communicate such information, and how they classify certain bits of information as either optional or mandatory. To deal with these differences EPCarts exposes an API that is intended to work with as many shopping carts as possible (regardless of how they are implemented - SAAS vs Plugin architecture, or the programming language used).

In this guide, you will find instructions about the information you need to provide to EPCarts, as well as the formatting we expect this information to be in. You will also find information on how to go about signing your request in order to protect against malicious attacks as well as session hijacking.

**NOTE** this guide assumes prior knowledge and familiarity with the shopping cart that EPCarts is to be integrated into. We understand that shopping carts vary in the way they are designed e.g. SAAS (Shopify) vs Plugin architecture (WooCommerce). You should still be able to integrate EPCarts into your choice of shopping cart regardless of these differences.
