# Signature Generation

This section includes information on the signing and verification methods that Oxipay uses. Oxipay uses HMAC-SHA256 for purposes of signing and verifying requests and responses. In this context:

* A key that is known to both the merchant using the particular shopping cart and Oxipay. This is also known as an API Key.

* A <code>message</code> which is a string of all key-value pairs that are stored alphabetically and are concatenated with seperators. Please note that we have adopted the convention of prefixing the various keys with <code>x_</code> similar to what is done in Shopify.

The resulting HMAC-SHA256 signature needs to be hex-encoded and passed along with the remainder of the transaction payload as a value of the key <code>x_signature</code>

# Example

Below is a example of what the payload might look like when posted from the shopping cart to the Oxipay payment gateway in URL encoded query string format.

	x_reference=123456789&x_account_id=1&x_amount=100.00&x_currency=AUD&x_url_callback=sample_callback_url&x_url_complete=sample_complete_url&x_shop_country=AU&x_shop_name=Sample+Shop&x_test=true&x_customer_first_name=first&x_customer_last_name=last&x_customer_email=sample%40email.com&x_customer_billing_country=AU&x_customer_billing_city=Adelaide&x_customer_billing_address1=97+Pirie&x_customer_billing_address2=St&x_customer_billing_state=SA&x_customer_billing_zip=5000&x_invoice=%123456789&x_description=Sample+Store+-+%123456789&x_url_cancel=sample_cancel_url&x_signature=dummysignaturelaskdjfhjnojelkfmlaksdf
