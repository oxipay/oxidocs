---
title: "Statuses and Codes"
menuTitle: "Statuses and Codes"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>Statuses and codes</h3>

There are 3 unique statuses as follows:

* **Success**: When the intent of the request is successful e.g. an Approval from the *ProcessAuthorisation* API.
* **Failed**: When the intent of the request is unsuccessful e.g. a Decline from the *ProcessAuthorisation* API.
* **Error**: When there is a problem with the request or an unexpected error.

The following table defines statuses, codes, and messages returned by the Oxipay APIs. The reason for the unique codes is to make life a bit easier for integrators that want to display their own custom messages.

Status | Code | API | Message
----------|----------|----------|----------
Success | SCRK01 | CreateKey | Success
Success | SINV01 | Invite | Success
Success | SPRA01 | ProcessAuthorisation | Approved
Success | SPSA01 | ProcessSalesAdjustment | Approved
Success | SPAR01 | ProcessSalesAdjustmentReversal | Approved
Success | SSER01 | SendReceipt | Success
Failed | FPRA01 | ProcessAuthorisation | Declined due to internal risk assessment against the customer
Failed | FPRA02 | ProcessAuthorisation | Declined due to insufficient funds for the deposit
Failed | FPRA03 | ProcessAuthorisation | Declined as communication to the bank is currently unavailable
Failed | FPRA04 | ProcessAuthorisation | Declined because the customer limit has been exceeded
Failed | FPRA05 | ProcessAuthorisation | Declined due to negative payment history for the customer
Failed | FPRA06 | ProcessAuthorisation | Declined because the credit-card used for the deposit is expired
Failed | FPRA07 | ProcessAuthorisation | Declined because supplied posTransactionRef has already been processed
Failed | FPRA08 | ProcessAuthorisation | Declined because the instalment amount was below the minimum threshold
Failed | FPRA09 | ProcessAuthorisation | Declined because purchase amount exceeded pre-approved amount
Failed | FPRA21 | ProcessAuthorisation | The Barcode was not found
Failed | FPRA22 | ProcessAuthorisation | The Barcode has already been used
Failed | FPRA23 | ProcessAuthorisation | The Barcode has expired
Failed | FPRA24 | ProcessAuthorisation | The Barcode has been cancelled
Failed | FPRA99 | ProcessAuthorisation | Declined
Failed | FPSA01 | ProcessSalesAdjustment | Unable to find the specified POS transaction reference
Failed | FPSA02 | ProcessSalesAdjustment | This contract has already been completed
Failed | FPSA03 | ProcessSalesAdjustment | This Oxipay contract has previously been cancelled and all payments collected have been refunded to the customer
Failed | FPSA04 | ProcessSalesAdjustment | Sales adjustment cannot be processed for this amount
Failed | FPSA05 | ProcessSalesAdjustment | Unable to process a sales adjustment for this contract. Please contact Merchant Services on [CollectionsPhone] during business hours for further information
Failed | FPSA06 | ProcessSalesAdjustment | Sales adjustment cannot be processed. Please call Oxipay Collections on [CollectionsPhone]
Failed | FPSA07 | ProcessSalesAdjustment | Sales adjustment cannot be processed at this store
Failed | FPSA08 | ProcessSalesAdjustment | Sales adjustment cannot be processed for this transaction. Duplicate receipt number found.
Failed | FPSA09 | ProcessSalesAdjustment | Amount must be greater than 0.
Failed | FPAR01 | ProcessSalesAdjustmentReversal | Unable to find the specified POS signature
Failed | FPAR02 | ProcessSalesAdjustmentReversal | This contract has already been completed
Failed | FPAR03 | ProcessSalesAdjustmentReversal | This Oxipay contract has previously been cancelled and all payments collected have been refunded to the customer
Failed | FPAR05 | ProcessSalesAdjustmentReversal | Unable to process a sales adjustment for this contract. Please contact Merchant Services on [CollectionsPhone] during business hours for further information
Failed | FPAR06 | ProcessSalesAdjustmentReversal | Sales adjustment adjustment cannot be processed. Please call Oxipay Collections on [CollectionsPhone]
Failed | FPAR07 | ProcessSalesAdjustmentReversal | Sales adjustment adjustment cannot be processed at this store
Failed | FPAR08 | ProcessSalesAdjustmentReversal | Sales adjustment adjustment cannot be processed for this transaction. Duplicate signature found.
Failed | FSER01 | SendReceipt | Unable to find the specified POS transaction reference
Failed | FSER02 | SendReceipt | The specified POS transaction reference is already in use
Failed | FCRK01 | CreateKey | Device token provided could not be found
Failed | FCRK02 | CreateKey | Device token provided has already been used
Error | EVAL01 | * | Validation error
Error | EVAL02 | ProcessAuthorisation  | Minimum finance amount is $20
Error | EAUT01 | * | Authentication error
Error | ESIG01 | * | Signature mismatch error
Error | EISE01 | * | Internal server error