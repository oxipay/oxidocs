# Signature Generation

In order to prevent against malicious attacks and session hijacking, Oxipay implements a signing mechanism based on HMAC-SHA256. This section includes information on the mechanism you need to implement to sign the transaction payload. 

As mentioned, Oxipay uses HMAC-SHA256 for purposes of signing and verifying requests and responses whereby the:

* <code>key</code> is the API key which is only known to Oxipay and the merchant intending to use Oxipay, this is sometimes referred to as the API Key.

* <code>message</code> is the string of all key-value pairs that represent the trasnaction payload, these keys are prefixed with <code>x_</code>, are sorted alphabetically and are concatenated with seperators.

The resulting HMAC-SHA256 signature needs to be hex-encoded and passed along with the remainder of the transaction payload as a value of the key <code>x_signature</code>

## PHP Example

Below is a PHP code snippet that demonstrates how a signature might be generated in the context of Oxipay:

```php
	function oxipay_sign($query, $api_key )
	{
	    $clear_text = '';
	    ksort($query);
	    foreach ($query as $key => $value) {
	        if (substr($key, 0, 2) === "x_") {
	            $clear_text .= $key . $value;
	        }
	    }
	    $hash = hash_hmac( "sha256", $clear_text, $api_key);
	    return str_replace('-', '', $hash);
	}
```

Note that the method expects two parameters <code>$query</code> and <code>$api_key</code> which represent the key-value pairs that represent the transaction payload information as well as the API Key that is only known by Oxipay and the merchant.

The method performs a sorting of the various key-value pairs maintaing the correlation between the various keys and their respective values. It then uses the <code>hash_hmac</code> method to generate a keyed has value using the HMAC method.

