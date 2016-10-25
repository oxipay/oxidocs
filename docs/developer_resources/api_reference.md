# API Reference

Communicating with Oxipay in order to process a transaction via our payment gateway involves **POST**ing a request to the Oxipay endpoint. This can be viewed as an authorisation request that is performed by the shopping cat in order to process the payment via Oxipay.

There are two Oxipay endpoints that transaction information can be posted to and these are the live (production) payment gateway and the test (sandbox) payment gateway.

## Oxipay Endpoints
The Production Oxipay endpoint is:<br> [https://secure.oxipay.com.au/Checkout?platform=Default](https://secure.oxipay.com.au/Checkout?platform=Default)

The Sandbox Oxipay endpoint is:<br> [https://xpozsecure.certegyezipay.com.au/Checkout?platform=Default](https://xpozsecure.certegyezipay.com.au/Checkout?platform=Default)

## Request POST Format

Posting to the Oxipay endpoing, regardless of whether this is done in the live or test environments, should be done in the <code>application/x-www-form-urlencoded</code> format whereby the queyr string will represent the body of the HTTP message that is sent to Oxipay. The various key-value pairs that represent the transaction payload are seperated by the <code>&</code> character whilst the key-value pairs are seperated by the <code>=</code> character. Note that Oxipay adopts the convention of prefixing the various key names with <code>x_</code> and we anticipate that you will adopt a similar convention when integrating Oxipay into your shopping cart.

Below is an overview of the various key-value combination that can be passed to Oxipay (**Request Values**), a description of what they are as well as an indication of whether they are mandatory or optional.

# Sample POST

Below is a sample request that might be posted to an Oxipay endpoing. Note that the POST is in the <code>application/x-www-form-urlencoded</code> format.


```URL
x_reference=123&x_account_id=1&x_amount=100.00&x_currency=AUD
&x_url_callback=sample_callback_url&x_url_complete=sample_complete_url
&x_shop_country=AU&x_shop_name=Sample+Shop&x_test=true
&x_customer_first_name=first&x_customer_last_name=last
&x_customer_email=sample%40email.com&x_customer_billing_country=AU
&x_customer_billing_city=Adelaide&x_customer_billing_address1=97+Pirie
&x_customer_billing_address2=St&x_customer_billing_state=SA
&x_customer_billing_zip=5000&x_invoice=%123
&x_description=Sample+Store+-+%123
&x_url_cancel=sample_cancel_url&x_signature=dummy_signature
```

## Request POST key-value pairs

 Key | Description | Type | Example
-----|-------------|------|---------
x_account_id **Required**         | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_amount **Required**             | Represents the transaction's total amount inc. any taxes and shipping costs | decimal | 99.90
x_currency **Required**           | Currency in which the transaction was processed | iso-4217 | AUD
x_customer_billing_address1       | Billing address, line 1 | unicode string | 97 Pirie St 
x_customer_billing_address2       | Billing address, line 2 | unicode string | Level 6 
x_customer_billing_city           | Billing city | unicode string | Adelaide 
x_customer_billing_country        | Billing country | iso-3166-1 alpha-2 | AU 
x_customer_billing_phone          | Billing phone number, can be mobile or landline | unicode string | 0400 000 000 
x_customer_billing_state          | Billing state | unicode string | SA 
x_customer_billing_zip            | Billing zip code | unicode string | 5000 |
x_customer_email                  | Billing email address | unicode string | dummy@gmail.com 
x_customer_first_name             | Customer's first name | unicode string | John 
x_customer_last_name              | Customer's last name | unicode string | Appleseed 
x_customer_phone                  | Customer's phone number | unicode string | 0400 000 000
x_customer_shipping_address1      | Shipping address, line 1 | unicode string | 97 Pirie St 
x_customer_shipping_address2      | Shipping address, line 2 | unicode string | Level 6 
x_customer_shipping_city          | Shipping city | unicode string | Adelaide 
x_customer_shipping_country       | Shipping country | unicode string | AU
x_customer_shipping_first_name    | Customer's first name (Shipping) | unicode string | John
x_customer_shipping_last_name     | Customer's last name (Shipping) | unicode string | Appleseed
x_customer_shipping_phone         | Customer's phone number (Shipping) | unicode string | 0400 000 000
x_customer_shipping_state         | Shipping state | unicode string | SA
x_customer_shipping_zip           | Shipping zip code | unicode string | 5000
x_description                     | Item's description as setup in the shopping cart | unicode string | Order #767
x_invoice                         | Transaction invoice number | unicode string | #767
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_shop_country **Required**       | Country of where the merchant's store is located | iso-3166-1alpha-2 | AU 
x_shop_name **Required**          | Store name as advertised on the internet, TV and other media | Shop Inc
x_signature **Required**          | Request payload that is signed/verified using HMAC-SHA256 | hex string, case-insensitive | 
x_test **Required**               | Indicates whether the transaciton is to be processed as a live or a test transaction | true/false | true  
x_url_callback **Required**       | Callback notifications are sent asynchronously to this URL | URL | shop.com.au/callback 
x_url_cancel **Required**         | Customers are redirected to this URL if they want to quit their Oxipay transaction and return to the shopping cart store instead | URL | shop.com.au/cancel 
x_url_complete **Required**       | Customers are redirected to this URL if they have successfully processed their transaction using Oxipay | URL | shop.com.au/compete 

## Response POST

Once a transaction has been processed by Oxipay, Oxipay will communicate with the shopping platform using the <code>x_url_callback</code> URL that is specified as part of the request POST. The response is also sent in the <code>application/x-www-form-urlencoded</code> format as an asynchronous POST. Similar to the request POST, the response POST includes key-values pairs that are specific to that transaction and indicate things such as the outcome of that particular transaction whether it has failed or is pending another action for instance.


## Response POST key-value pairs

Below is an overview of the various response key-value pairs that Oxipay returns after it has finished processing a transaction. Note that some of these key-value pairs echo corresponding key-value pairs in the request that Oxipay receives - as is the case with <code>x_currency</code> for instance.

 Key | Description | Type | Example
-----|-------------|------|---------
x_account_id **Required**         | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_currency **Required**           | Currency in which the transaction was processed | iso-4217 | AUD
x_test **Required**               | Indicates whether the transaciton is to be processed as a live or a test transaction | true/false | true
x_amount **Required**             | Represents the transaction's total amount inc. any taxes and shipping costs | decimal | 99.90  
x_gateway_reference **Required**  | A reference for the authorisation issues by Oxipay that is unique | unique string | 123
x_timestamp **Required**          | Time at which the transaction is completed, in UTC format YYYY-MM-DDTHH:MM:SSZ | iso-8601 in UTC | 2017-06-24T12:11:43Z
x_result **Required**             | Values that represent the outcome of a transaction | Valid values are **completed**, **failed** and **pending** | **failed**
x_message **Required**            | A custom error message that is displayed to the end user | ascii string | Signature Invalid



