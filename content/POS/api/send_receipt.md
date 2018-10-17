---
title: "Send Receipt"
menuTitle: "Send Receipt"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

Requests to this API should only be made when a temporary value is used as the *x_pos_transaction_ref* in calls to *ProcessAuthorisation*. Oxipay will store the specified *x_receipt_number*, which it will use for transaction reconciliation in any future requests to *ProcessSalesAdjustment*.

**Method:** *SendReceipt*

<h3>Request</h3>

Parameter | Type | Length | Description
----------|------|--------|------------
x_pos_transaction_ref | Unicode string | 64 | This must be the same reference used in *ProcessAuthorisation* request.
x_merchant_id | Unicode string | 10 | Merchant identifier as defined by Oxipay
x_device_id | Unicode string | 64 | Unique device identifier for the POS terminal
x_operator_id | Unicode string | 64 | ID of POS/terminal operator
x_firmware_version | Unicode string | 64 | current firmware version of POS device
x_receipt_number | Unicode string | 64 | This must be the same reference (x_pos_transaction_ref) that would get passed through on future ProcessSalesAdjustment requests
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

Request -> x_receipt_number | Response -> x_status | Response -> x_code
-----------|-----------|-----------
01###### | Success | SSER01
10###### | Failed | FSER01
11###### | Failed | FSER02
30###### | Error | EVAL01
31###### | Error | EAUT01
any other value | Error | EISE01

<span style="color:grey;"><b>#</b> signifies an alphanumeric digit</span>

**Testing Assumptions**

* To generate the signature, use a device-signing-key of "1234567890". A invalid signature will cause an ESIG01 Error.
