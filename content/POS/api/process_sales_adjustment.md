---
title: "Process Sales Adjustment"
menuTitle: "Process Sales Adjustment"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

This endpoint is used to process a Sales Adjustment at the point-of-sale. See <a href="/process/sales_adjustment/">sales adjustment process</a> for more information.

**Method:** *ProcessSalesAdjustment*

<h3>Request</h3>

Parameter | Type | length | Description
----------|------|--------|------------
x_pos_transaction_ref | Unicode string | 64 | This is the transaction reference of the sales adjustment
x_purchase_ref | Unicode string | 64 | The original transaction reference.<br/>It can either be the x_pos_transaction_ref that was passed through as part of the *ProcessAuthorisation* request (or the *SendReceipt* request), or the Oxipay purchase number that was returned from the call to *ProcessAuthorisation*. In the case of the former, the x_pos_transaction_ref *must* be unique among all sellers in a chain of sellers. In the case of the latter, the POS software would be required to store the x_purchase_numer retured by *ProcessAuthorisation*.
x_merchant_id | Unicode string | 10 | Merchant identifier as defined by Oxipay
x_amount | int | 12 | Requested adjustment amount (in cents)
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
x_message | Unicode string | A string explaining the status/code above. Example: For an Error: Reason why the adjustment cannot be done
tracking_data | Associative array | Echoes tracking_data sent on the request
signature | Hex string case-insensitive | Payload that is signed using HMAC-SHA256 using a device specific key

<h3>Testing</h3>

The following describes dummy API requests that return a predictable response. Please contact <a href="mailto:support@{{< domain >}}">support@{{< domain >}}</a> to get access to the test/dummy APIs.

Request -> x_amount | Response -> x_status | Response -> x_code
-----------|-----------|-----------
##01 | Success | SPSA01
##10 | Failed | FPSA01
##11 | Failed | FPSA02
##12 | Failed | FPSA03
##13 | Failed | FPSA04
##14 | Failed | FPSA05
##15 | Failed | FPSA06
##16 | Failed | FPSA07
##17 | Failed | FPSA08
##18 | Failed | FPSA09
##30 | Error | EVAL01
##31 | Error | EAUT01
any other value | Error | EISE01

<span style="color:grey;"><b>#</b> signifies a numeric digit</span>

**Testing Assumptions**

* To generate the signature, use a device-signing-key of "1234567890". A invalid signature will cause an ESIG01 Error.
