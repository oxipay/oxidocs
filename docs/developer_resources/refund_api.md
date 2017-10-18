# Refund API

Oxipay provides an API to programmatically process refunds or adjustments to an Oxipay purchase.

## Oxipay Endpoints


| Oxipay Environment | URL |
|--------------------|-----|
| Production Endpoint | [https://portals.%domain%/api/ExternalRefund](https://secure.%domain%/api/ExternalRefund) |
| Sandbox Endpoint | [https://portalssandbox.%domain%/api/ExternalRefund](https://securesandbox.%domain%/api/ExternalRefund) |


## Request 

### Headers

| Key          | Value            |
|--------------|------------------|
| Content-Type | application/json |

### Body

    {
        "x_merchant_number": "30199250",
        "x_purchase_number": "52004168",
        "x_amount": "10.00",
        "x_reason": "Test refund",
        "signature": "e39ae5f3233f561162836989e050c1b61ba9e3d5eb3d64d4b3701e95fb5850a1"
    }

See [Signature Generation](signature_generation.md) for information on how to generate the HMAC Signature. 

## Response 

| HTTP Status | Reason Code | Reason Description|
|-------------|-------------|-------------------|
|  204        |   none      |   Success         |
|  400        | MERR0001    | API Key Not found |
|  400        | MERR0003    | Refund Failed     |
|  400        | MERR0004    | Invalid Request   |
|  401        | none        | Failed Signature Check|


## Example

The following ``curl`` command will allow you to test the refunds API. You will need to substitute **your** x_merchant_number, x_purchase_number and signature

    curl \
    --header "Content-Type:application/json" \
    --request POST \
    --data '{
        "x_merchant_number": "30199250",
        "x_purchase_number": "52000152",  
        "x_amount": 45.00,
        "x_reason": "test",
        "signature": "a5fc92ddd2326c6099bd0f43bbe75afb54004a6ba68f354cc2b40328341d8ee2"
    }' \    
    https://portalssandbox.oxipay.com.au/api/ExternalRefund

