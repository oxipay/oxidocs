# Signing Mechanism

This section includes information on the signing and verification methods that Oxipay uses. Oxipay uses HMAC-SHA256 for purposes of signing and verifying requests and responses. In this context:

* A key that is known to both the merchant using the particular shopping cart and Oxipay. This is also known as an API Key.

* A <code>message</code> which is a string of all key-value pairs that are stored alphabetically and are concatenated with seperators. Please note that we have adopted the convention of prefixing the various keys with <code>x_</code> similar to what is adopted by Shopify.

The resulting HMAC-SHA256 signature needs to be hex-encoded and passed along with the remainder of the transaction payload as a value of the key <code>x_signature</code>