---
title: "Invite"
menuTitle: "Invite"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

This endpoint is used to initiate a request that will send an invite to the customer to Login or Register with Oxipay so that they can get a pre-approval code.

**Method:** *Invite*

<h3>Request</h3>

Parameter | Type | length | Description
----------|------|--------|------------
x_merchant_id | Unicode string | 10 | Merchant identifier as defined by Oxipay
x_mobile | Unicode string | 10 | Customer’s mobile number
x_purchase_amount | int | 12 | Total purchase amount (in cents)
x_device_id | Unicode string | 64 | Unique device identifier for the POS terminal
x_operator_id | Unicode string | 64 | ID of POS/terminal operator
x_firmware_version | Unicode string | 64 | current firmware version of POS device
tracking_data <code class="optional">optional</code> | Associative array | Max 1000000 | A map that can be populated with additional tracking/state information that will get passed back in the response
signature | Hex string case-insensitive | 200 | Payload that is signed using HMAC-SHA256 using a device specific key

<h3>Response</h3>

Parameter | Type | Description
-----------|------|-------------
x_status | Unicode string | Success/Failure/Error
x_code | Unicode string | A code that maps to a <a href="/api_information/status_codes/">specific reason</a>
x_message | Unicode string | A string explaining the status/code above. 
tracking_data | Associative array | Echoes tracking_data sent on the request
signature | Hex string case-insensitive | Payload that is signed using HMAC-SHA256 using a device specific key

<h3>Testing</h3>

The following describes dummy API requests that return a predictable response. Please contact <a href="mailto:support@{{< domain >}}">support@{{< domain >}}</a> to get access to the test/dummy APIs.

Request -> x_purchase_amount | Response -> x_status | Response -> x_code
-----------|-----------|-----------
##01 | Success | SINV01
##30 | Error | EVAL01
##31 | Error | EAUT01
any other value | Error | EISE01

<span style="color:grey;"><b>#</b> signifies a numeric digit</span>

**Testing Assumptions**

* To generate the signature, use a device-signing-key of "1234567890". A invalid signature will cause an ESIG01 Error.
