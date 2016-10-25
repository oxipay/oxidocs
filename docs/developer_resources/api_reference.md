# API Reference

Communicating with Oxipay in order to process a transaction via our payment gateway involves **POST**ing a request to the Oxipay endpoint. This can be viewed as an authorisation request that is performed by the shopping cat in order to process the payment via Oxipay.

Below is an overview of the various key-value combinations that can be passed to Oxipay (**Request Values**), a description of what they are as well as an indication of whether they are mandatory or optional. Please note that Oxipay adopts the convention of pre-fixing the various key names with <code>x_</code>

## Request Values

 Key | Description | Type | Example
-----|-------------|------|---------
x_account_id **Required**         | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_amount **Required**             | Represents the transaction's total amount inc. any taxes and shipping costs | decimal | 99.90
x_currency **Required**           | Currency in which the transaction was processed | iso-4217 | AUD
x_customer_billing_address1       | Customer's billing address, line 1 | unicode string | 97 Pirie St 
x_customer_billing_address2       | Customer's billing address, line 2 | unicode string | Level 6 
x_customer_billing_city           | Customer's billing city | unicode string | Adelaide 
x_customer_billing_country        | Customer's billing country | iso-3166-1 alpha-2 | AU 
x_customer_billing_phone          | Customer's billing phone number, can be mobile or landline | unicode string | 0400 000 000 
x_customer_billing_state          | Customer's billing state | unicode string | SA 
x_customer_billing_zip            | Customer's billing zip code | unicode string | 5000 |
x_customer_email                  | Customer's billing email address | unicode string | dummy@gmail.com 
x_customer_first_name             | Customer's first name | unicode string | John 
x_customer_last_name              | Customer's last name | unicode string | Appleseed 
x_customer_phone                  | Customer's phone number | unicode string | 0400 000 000
x_customer_shipping_address1      | Customer's shipping address, line 1 | unicode string | 97 Pirie St 
x_customer_shipping_address2      | Customer's shipping address, line 2 | unicode string | Level 6 
x_customer_shipping_city          | Customer's shipping city | unicode string | Adelaide 
x_customer_shipping_country       | Customer's shipping country | unicode string | AU
x_customer_shipping_first_name    | Customer's first name (Shipping) | unicode string | John
x_customer_shipping_last_name     | Customer's last name (Shipping) | unicode string | Appleseed
x_customer_shipping_phone         | Customer's phone number (Shipping) | unicode string | 0400 000 000
x_customer_shipping_state         | Customer's shipping state | unicode string | SA
x_customer_shipping_zip           | Customer's shipping zip code | unicode string | 5000
x_description                     | Item's description as setup in the shopping cart | unicode string | Order #767
x_invoice                         | Transaction invoice number | unicode string | #767
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_shop_country **Required**       | Country of where the merchant's store is located | iso-3166-1alpha-2 | AU 
x_shop_name **Required**          | Store name as advertised on the internet, TV and other media | Shop Inc
x_signature **Required**          | Request payload that is signed/verified using HMAC-SHA256 | hex string, case-insensitive | 
x_test **Required**               | Indicates whether the transaciton is to be processed as a live or a test transaction | true/false | true  
x_url_callback **Required**       | Callback notifications are sent asynchronously to this URL | URL | oxipay.com.au/callback 
x_url_cancel **Required**         | Customers are redirected to this URL if they want to quit their Oxipay transaction and return to the shopping cart store instead | URL | oxipay.com.au/cancel 
x_url_complete **Required**       | Customers are redirected to this URL if they have successfully processed their transaction using Oxipay | URL | oxipay.com.au/compete 

## Response Values

Below is an overview of the various response values that Oxipay returns when processing a transaction. Note that some of these key-value pairs echo corresponding key-value pairs in the request that Oxipay receives - as is the case with <code>x_currency</code> for instnace.

 Key | Description | Type | Example
-----|-------------|------|---------
x_account_id **Required**         | This is the Merchant ID assigned by Oxipay to the merchant | unicode string | 123456
x_reference **Required**          | A reference that uniquely references the order and assigned by the merchant | ascii string | 19783
x_currency **Required**           | Currency in which the transaction was processed | iso-4217 | AUD
x_test **Required**               | Indicates whether the transaciton is to be processed as a live or a test transaction | true/false | true  







