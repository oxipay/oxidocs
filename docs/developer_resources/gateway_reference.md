# Gateway Reference

Communicating with Oxipay in order to process a transaction via our payment gateway involves **the buyers' browser** performing an HTTP **POST** to the Oxipay endpoint. This can be viewed as an authorisation request that is performed by the shopping cart in order to process the payment via Oxipay.

Please note, this is not an HTTP API and *can not* be used for server to server communication.

There are two Oxipay gateways that transaction information can be posted to and they represent the live Oxipay payment gateway and the test (sandbox) gateway.

## Oxipay Gateways


| Oxipay Environment | URL |
|--------------------|-----|
| Production Gateway | [https://secure.%domain%/Checkout?platform=Default](https://secure.%domain%/Checkout?platform=Default) |
| Sandbox Gateway | [https://securesandbox.%domain%/Checkout?platform=Default](https://securesandbox.%domain%/Checkout?platform=Default) |

<a name="Responses"></a>

## Request POST

Posting to the Oxipay endpoint, regardless of whether this is done in the live or test environment, should be done using the format <code>application/x-www-form-urlencoded</code>. Please note that Oxipay adopts the convention of prefixing the various key names with <code>x_</code> .

Below is an overview of the various key-value pairs that can be passed to Oxipay (**Request Values**), a description of what they are as well as an indication of whether they are mandatory or optional.

## Request values

 Key | Description | Type | Example | Length
-----|-------------|------|---------|--------
x_account_id **Required**         | This is a unique Merchant ID that is assigned by Oxipay to individual merchants | unicode string | 123456 | 10
x_amount **Required**             | Represents the transaction's total amount including any taxes and shipping costs | decimal | 99.90 | 12
x_currency **Required**           | Currency of the transaction | ISO-4217 | %currency_abbr% | 3
x_customer_billing_address1       | Billing address line 1 | unicode string | %address_street_1% | 200
x_customer_billing_address2       | Billing address line 2 | unicode string | %address_street_2% | 200
x_customer_billing_city           | Billing city | unicode string | %address_city% | 200 
x_customer_billing_country        | Billing country | iso-3166-1 alpha-2 | %country_abbr% | 3
x_customer_billing_state          | Billing state | unicode string | %address_state_abbr% | 200 
x_customer_billing_postcode       | Billing postcode | unicode string | %address_post_code% | 200
x_customer_email                  | Billing email address | unicode string | user@example.com | 65
x_customer_first_name             | Customer's first name | unicode string | John | 50
x_customer_last_name              | Customer's last name | unicode string | Appleseed | 50
x_customer_phone                  | Customer's phone number | unicode string | %address_phone_number% | 12 
x_customer_shipping_address1      | Shipping address line 1 | unicode string | %address_street_1% | 200 
x_customer_shipping_address2      | Shipping address line 2 | unicode string | %address_street_2% |  200 
x_customer_shipping_city          | Shipping city | unicode string | %address_city% | 200
x_customer_shipping_country       | Shipping country | unicode string | %country_abbr% | 3
x_customer_shipping_first_name    | Customer's first name (Shipping) | unicode string | John | 50
x_customer_shipping_last_name     | Customer's last name (Shipping) | unicode string | Appleseed | 50
x_customer_shipping_phone         | Customer's phone number (Shipping) | unicode string | %address_phone_number% | 12 
x_customer_shipping_state         | Shipping state | unicode string | %address_state_abbr% | 200
x_customer_shipping_postcode      | Shipping postcode | unicode string | %address_post_code% | 200
x_description                     | Item's description as setup in the shopping cart | unicode string | Order #767 | 200
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant. This is unique to the shopping cart. | ascii string (max length 250 bytes) | 19783 | 250
x_shop_country **Required**       | Country of where the merchant's store is located | iso-3166-1alpha-2 | %country_abbr% | 3
x_shop_name **Required**          | Store name as advertised on the internet, TV and other media | Shop Inc | 200
x_signature **Required**          | Request payload that is signed/verified using HMAC-SHA256 | hex string, case-insensitive | See [Signature Generation](../signature_generation/) | 64
x_url_callback **Required**       | Callback notifications are sent asynchronously to this URL. **The protocol must be HTTPS** | URL | https://shop%domain_postfix%/callback | 200
x_url_cancel **Required**         | Customers are redirected to this URL if they want to quit their Oxipay transaction and return to the shopping cart store instead | URL | https://shop%domain_postfix%/cancel | 200
x_url_complete **Required**       | Customers are redirected to this URL if they have successfully processed their transaction using Oxipay | URL | https://shop%domain_postfix%/compete | 200
x_transaction_timeout             | Transaction timout in minutes. Maximum value is 1440. | int | 60

# Sample POST

Below is a sample request that might be posted to an Oxipay gateway that is in the <code>application/x-www-form-urlencoded</code> format. In this example, please ignore values for individual keys - such as the value for <code>x_signature</code> - since this sample POST is for demonstration purposes only and does not demonstrate a real transaction that can be completed by Oxipay.


    x_reference=123&x_account_id=1&x_amount=100.00&x_currency=%currency_abbr%&x_url_callback=sample_callback_url&x_url_complete=sample_complete_url&x_shop_country=%country_abbr%&x_shop_name=Sample+Shop&x_customer_first_name=first&x_customer_last_name=last&x_customer_email=sample%40email.com&x_customer_billing_country=%country_abbr%&x_customer_billing_city=%address_city%&x_customer_billing_address1=97+Pirie&x_customer_billing_address2=St&x_customer_billing_state=%address_state_abbr%&x_customer_billing_zip=%address_post_code%&x_description=Sample+Store+-+%123&x_url_cancel=sample_cancel_url&x_signature=dummy_signature


<a name="Responses"></a>
## POST and GET responses

There are two responses from Oxipay.

The first response that Oxipay always performs is a server-to-server asynchronous POST to the shopping cart on the gateway specified in the <code>x_url_callback</code> and in the format <code>application/x-www-form-urlencoded</code>. Similar to the request POST, the response POST includes key-values pairs that are specific to that transaction and indicate things such as the outcome of that particular transaction if it has failed or is completed successfully for instance.</br>
Please note that this POST must be sent over HTTPS. Consequently the <code>x_url_callback</code> field should specify the HTTPS has the protocol.

The second response is a HTTP GET to the client on either of the URLs specified in <code>x_url_complete</code> or <code>x_url_cancel</code>.

## Response POST values

Below is an overview of the various response key-value pairs that Oxipay returns after it has finished processing a transaction. Note that some of these key-value pairs echo corresponding key-value pairs in the request that Oxipay receives - as is the case with <code>x_currency</code> for instance.

 Key | Description | Type | Example
-----|-------------|------|---------
x_account_id              | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_reference               | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_currency                | Currency of the transaction | ISO-4217 | %currency_abbr%
x_test                    | Indicates whether the transaction is to be processed as a live or a test transaction | True/False | False
x_amount                  | Represents the transaction's total amount including any taxes and shipping costs | decimal | 99.90  
x_gateway_reference       | A reference for the authorisation issues by Oxipay that is unique | unique string | 123
x_timestamp               | Time at which the transaction is completed, in UTC format YYYY-MM-DDTHH:MM:SSZ | iso-8601 in UTC | 2017-06-24T12:11:43Z
x_result                  | Values that represent the outcome of a transaction | Valid values are **completed** or **failed** | **completed**
x_signature               | Response payload that is signed/verified using HMAC-SHA256 | hex string, case-insensitive | See [Signature Generation](../signature_generation/)

## Response POST reply

It is expected that the POST reponse will be replied to by the sellers server to confirm that the POST response was recieved.<br>
The expected key-value pairs of this reply are listed below.

 Key | Description | Type | Example
-----|-------------|------|---------
x_reference               | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_result                  | Values that represent the outcome of a transaction | Valid values are **completed** and **failed**| **completed**
