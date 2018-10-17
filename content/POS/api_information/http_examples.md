---
title: "HTTP Examples"
menuTitle: "HTTP Examples"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>HTTP Examples</h3>

CreateKey
===================================================================================================
<code class="post-icon mr">POST</code>**/webapi/v1/CreateKey**

Used to obtain a device-signing-key using the shared private key. The device-signing-key can then be used to digitally sign all subsequent messages. See <a href="/api/create_key/">Create Key</a> for more information.

*Sample JSON request:*
```
{
   "x_merchant_id": "30299999",
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "x_device_token": "nb4i6ldxuVQC",
   "x_pos_vendor": "Pos Provider",
   "signature": "cf4f4a19662c7617ea83a47456934123f530c82cdfdd66f5b706dd2263806848"
}
```

*Sample JSON reponse:*
```
{
   "x_key": "dy33vQhksVsv",
   "x_status": "Success",
   "x_code": "SCRK01",
   "x_message": "Success",
   "signature": "c8340d19b24f8ec2fb915202ea7fb08d81fc711681fbfea297106d219a5c30a6",
   "tracking_data": null
}
```

ProcessAuthorisation
===================================================================================================

<code class="post-icon mr">POST</code>**/webapi/v1/ProcessAuthorisation**

Processes an authorisation to finalise the transaction. See <a href="/api/process_authorisation/">Process Authorisation</a> for more information.

*Sample JSON request:*
```
{
   "x_merchant_id": "30299999",
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "x_pos_transaction_ref": "tnx-ref1",
   "x_pre_approval_code": "6111NHQMAM4Z",
   "x_finance_amount": 10000,
   "x_purchase_amount": 50000,
   "purchase_items": "{ \"PurchaseItems\": [ \"Item1\", \"Item2\" ] }",
   "signature": "d6967970b99e585fc7d1a11702690f25b4be0c5fbfd10b39fbea3953ba48bad2"
}
```

*Sample JSON reponse:*
```
{
   "x_status": "Success",
   "x_code": "SPRA01",
   "x_message": "Approved",
   "signature": "07fa5c9b43520bb9417d7eadb8390a87bf7a42767a67bd5af95627b51c2d8bae",
   "tracking_data": null
}
```

Invite
===================================================================================================

<code class="post-icon mr">POST</code>**/webapi/v1/Invite**

Initiates a request that will send an invite to the customer to Login or Register with Oxipay so that they can get a pre-approval code. See <a href="/api/invite/">Invite</a> for more information.

*Sample JSON request:*
```
{
   "x_merchant_id": "30299999",
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "x_mobile": "0400000000",
   "x_purchase_amount": 10000,
   "signature": "9acbc32115e19c3135738bbef891c864ef734e2f66c3c3d3aeb5e0b1982db5f4"
}
```

*Sample JSON reponse:*
```
{
   "x_status": "Success",
   "x_code": "SINV01",
   "x_message": "Success",
   "signature": "2e7ddc54f5457b22fcdd7382ce4e9651abd527051dbc069a3171b4201d8e359c",
   "tracking_data": null
}
```

SendReceipt
===================================================================================================

<code class="post-icon mr">POST</code>**/webapi/v1/SendReceipt**

See <a href="/api/send_receipt/">Send Receipt</a> for more information.

*Sample JSON request:*
```
{
   "x_merchant_id": "30299999",
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "x_pos_transaction_ref": "tnx-ref1",
   "x_receipt_number": "NewReceipt",
   "signature": "ac164e40585474838641bde1ad9bab08b6e6e0ab0c2dae814298e4fcef9c52fa"
}
```

*Sample JSON reponse:*
```
{
   "x_status": "Success",
   "x_code": "SSER01",
   "x_message": "Success",
   "signature": "b55c8cbe59305d3d8abc6ea8f0cdcf4702059d6d2fa935c83595e56e7001157b",
   "tracking_data": null
}
```

ProcessSalesAdjustment
===================================================================================================

<code class="post-icon mr">POST</code>**/webapi/v1/ProcessSalesAdjustment**

Used to process a Sales Adjustment as the point-of-sale. See <a href="/api/process_sales_adjustment/">Process Sales Adjustment</a> for more information.

*Sample JSON request:*
```
{
   "x_pos_transaction_ref": "tnx-ref1",
   "x_purchase_ref": "123456789",
   "x_merchant_id": "30299999",
   "x_amount": 1000,
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "signature": "ce20e2f1a9fe0d92b3d021ba7f1b372b006778cfab5fc4c09efa60a6d910c471"
}
```

*Sample JSON reponse:*
```
{
   "x_status": "Failed",
   "x_code": "FPSA05",
   "x_message": "Unable to process a sales adjustment for this contract. Please contact Merchant Services on [CollectionsPhone] during business hours for further information",
   "signature": "b490b0565a93b31bdf93037ede44b3619f08a1e0e5f68332db52f02176a86bb2",
   "tracking_data": null
}
```


ProcessSalesAdjustmentReversal
===================================================================================================

<code class="post-icon mr">POST</code>**/webapi/v1/ProcessSalesAdjustmentReversal**

Used to process a Sales Adjustment as the point-of-sale. See <a href="/api/process_adjustment_reversal/">Process Sales Adjustment Reversal</a> for more information.

*Sample JSON request:*
```
{
   "x_pos_transaction_ref": "tnx-rev1",
   "x_adjustment_signature": "ce20e2f1a9fe0d92b3d021ba7f1b372b006778cfab5fc4c09efa60a6d910c471",
   "x_merchant_id": "30299999",
   "x_device_id": "d555",
   "x_operator_id": "test_operator",
   "x_firmware_version": "123",
   "signature": "1949a14cfdd8e6062a54f28ab3a607637f081afb7b8f4cffa3fb413fadab963b"
}
```

*Sample JSON reponse:*
```
{
   "x_status": "Failed",
   "x_code": "FPSA05",
   "x_message": "Unable to process a sales adjustment reversal for this contract. Please contact Merchant Services on [CollectionsPhone] during business hours for further information",
   "signature": "1949a14cfdd8e6062a54f28ab3a607637f081afb7b8f4cffa3fb413fadab963b",
   "tracking_data": null
}
```