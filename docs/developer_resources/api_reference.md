# API Reference

Communicating with Oxipay in order to process a transaction via our payment gateway involves **POST**ing a request to the Oxipay endpoint. This can be viewed as an authorisation request that is performed by the shopping cart in order to process the payment via Oxipay.

There are two Oxipay endpoints that transaction information can be posted to and they represent the live Oxipay payment gateway and the test (sandbox) gateway.

## Oxipay Endpoints

Posting a request to the live payment gateway with the <code>x_test</code> set to <code>false</code> will process a real transaction. This means the credit card that was used as part of the checkout process will be debited. On the other hand, posting to the test gateway simulates a transaction and is not processed as a real transaction; that is, no real dollar amount will be debited from the specified credit card.

To test Oxipay, you are not only limited to the test (sandbox) URL. You can also use the live payment gateway but enable the <code>x_test</code> flag. Enabling the <code>x_test</code> flag will process the transaction via the live gateway but no real dollar amounts are debited from the credit card.

| Oxipay Environment | URL |
|--------------------|-----|
| Production Endpoint | [https://secure.oxipay.com.au/Checkout?platform=Default](https://secure.oxipay.com.au/Checkout?platform=Default) |
| Sandbox Endpoint | [https://xpozsecure.certegyezipay.com.au/Checkout?platform=Default](https://xpozsecure.certegyezipay.com.au/Checkout?platform=Default) |

## Request POST

Posting to the Oxipay endpoint, regardless of whether this is done in the live or test environment, should be done using the format <code>application/x-www-form-urlencoded</code>. Please note that Oxipay adopts the convention of prefixing the various key names with <code>x_</code> .

Below is an overview of the various key-value pairs that can be passed to Oxipay (**Request Values**), a description of what they are as well as an indication of whether they are mandatory or optional.

## Request values

 Key | Description | Type | Example
-----|-------------|------|---------
x_merchant_id **Required**         | This is a unique Merchant ID that is assigned by Oxipay to individual merchants | unicode string | 123456
x_amount **Required**             | Represents the transaction's total amount including any taxes and shipping costs | decimal | 99.90
x_customer_billing_address1       | Billing address line 1 | unicode string | 97 Pirie St 
x_customer_billing_address2       | Billing address line 2 | unicode string | Level 6 
x_customer_billing_city           | Billing city | unicode string | Adelaide 
x_customer_billing_country        | Billing country | iso-3166-1 alpha-2 | AU 
x_customer_billing_state          | Billing state | unicode string | SA 
x_customer_billing_postcode       | Billing postcode | unicode string | 5000 |
x_customer_email                  | Billing email address | unicode string | dummy@gmail.com 
x_customer_first_name             | Customer's first name | unicode string | John 
x_customer_last_name              | Customer's last name | unicode string | Appleseed 
x_customer_phone                  | Customer's phone number | unicode string | 0400 000 000
x_customer_shipping_address1      | Shipping address line 1 | unicode string | 97 Pirie St 
x_customer_shipping_address2      | Shipping address line 2 | unicode string | Level 6 
x_customer_shipping_city          | Shipping city | unicode string | Adelaide 
x_customer_shipping_country       | Shipping country | unicode string | AU
x_customer_shipping_first_name    | Customer's first name (Shipping) | unicode string | John
x_customer_shipping_last_name     | Customer's last name (Shipping) | unicode string | Appleseed
x_customer_shipping_phone         | Customer's phone number (Shipping) | unicode string | 0400 000 000
x_customer_shipping_state         | Shipping state | unicode string | SA
x_customer_shipping_postcode      | Shipping postcode | unicode string | 5000
x_description                     | Item's description as setup in the shopping cart | unicode string | Order #767
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant. This is unique to the shopping cart. | ascii string | 19783
x_shop_country **Required**       | Country of where the merchant's store is located | iso-3166-1alpha-2 | AU 
x_shop_name **Required**          | Store name as advertised on the internet, TV and other media | Shop Inc
x_signature **Required**          | Request payload that is signed/verified using HMAC-SHA256 | hex string, case-insensitive | See [Signature Generation]()
x_test **Required**               | Indicates whether the transaciton is to be processed using the live or test Oxipay endpoint | true/false | true  
x_url_callback **Required**       | Callback notifications are sent asynchronously to this URL | URL | shop.com.au/callback 
x_url_cancel **Required**         | Customers are redirected to this URL if they want to quit their Oxipay transaction and return to the shopping cart store instead | URL | shop.com.au/cancel 
x_url_complete **Required**       | Customers are redirected to this URL if they have successfully processed their transaction using Oxipay | URL | shop.com.au/compete 

# Sample POST

Below is a sample request that might be posted to an Oxipay endpoint that is in the <code>application/x-www-form-urlencoded</code> format. In this example, please ignore values for individual keys - such as the value for <code>x_signature</code> - since this sample POST is for demonstration purposes only and does not demonstrate a real transaction that can be completed by Oxipay.

<hr>
<div style="font-family: monospace; font-size:1.2rem; color: #DC143C; word-wrap: break-word !important;">
x_reference=123&x_account_id=1&x_amount=100.00&x_currency=AUD&x_url_callback=sample_callback_url&x_url_complete=sample_complete_url&x_shop_country=AU&x_shop_name=Sample+Shop&x_test=true&x_customer_first_name=first&x_customer_last_name=last&x_customer_email=sample%40email.com&x_customer_billing_country=AU&x_customer_billing_city=Adelaide&x_customer_billing_address1=97+Pirie&x_customer_billing_address2=St&x_customer_billing_state=SA&x_customer_billing_zip=5000&x_invoice=%123
&x_description=Sample+Store+-+%123&x_url_cancel=sample_cancel_url&x_signature=dummy_signature
</div>
<hr>

## POST and GET Responses

Note that that there are two responses from Oxipay. The first response that Oxipay always performs is a server-to-server asynchronous POST to the shopping cart on the endpoint specified in the <code>x_url_callback</code> and in the format <code>application/x-www-form-urlencoded</code>. Similar to the request POST, the response POST includes key-values pairs that are specific to that transaction and indicate things such as the outcome of that particular transaction if it has failed or is completed successfully for instance.

The second response is a HTTP GET to the client on either of the URLs specified in <code>x_url_complete</code> or <code>x_url_cancel</code>.

## Response POST values

Below is an overview of the various response key-value pairs that Oxipay returns after it has finished processing a transaction. Note that some of these key-value pairs echo corresponding key-value pairs in the request that Oxipay receives - as is the case with <code>x_currency</code> for instance.

 Key | Description | Type | Example
-----|-------------|------|---------
x_merchant_id **Required**         | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_test **Required**               | Indicates whether the transaction is to be processed as a live or a test transaction | true/false | true
x_amount **Required**             | Represents the transaction's total amount including any taxes and shipping costs | decimal | 99.90  
x_gateway_reference **Required**  | A reference for the authorisation issues by Oxipay that is unique | unique string | 123
x_timestamp **Required**          | Time at which the transaction is completed, in UTC format YYYY-MM-DDTHH:MM:SSZ | iso-8601 in UTC | 2017-06-24T12:11:43Z
x_result **Required**             | Values that represent the outcome of a transaction | Valid values are **completed**, **failed** and **pending** | **failed**



