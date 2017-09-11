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
        "MerchantNumber": "30199250",
        "PurchaseNumber": "52004168",
        "Amount": "10.00",
        "Reason": "Test refund",
        "Signature": "e39ae5f3233f561162836989e050c1b61ba9e3d5eb3d64d4b3701e95fb5850a1"
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

The following ``curl`` command will allow you to test the refunds API. You will need to substitude **your** MerchantNumber, PurchaseNumber and Signature

    curl \
    --header "Content-Type:application/json" \
    --request POST \
    --data '{
        "MerchantNumber": "30199250",
        "PurchaseNumber": "52004168",
        "Amount": "10.00",
        "Reason": "Test refund",
        "Signature": "e39ae5f3233f561162836989e050c1b61ba9e3d5eb3d64d4b3701e95fb5850a1"
    }' \
    https://portalssandbox.oxipay.com.au/api/ExternalRefund

