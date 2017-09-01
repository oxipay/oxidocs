# Signature Generation

In order to prevent against malicious attacks and hijacking of browser sessions,  EPCarts implements a signing mechanism based on HMAC-SHA256. This section provides information on how you can use HMAC-SHA256 for signing and verification purposes.

As mentioned, EPCarts uses HMAC-SHA256 for purposes of signing and verifying requests.

Below is an example that demonstrates how you can go about implementing a method in a shopping platform that is based on PHP to generate the signature.

## PHP Example

Below is a PHP code snippet that demonstrates how a signature might be generated in the context of EPCarts:

```php
	function EPCarts_sign($query, $api_key )
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

First note that the method expects two parameters and they are <code>$query</code> and <code>$api_key</code>. The <code>$query</code> represents the various key-value pairs that form your HTTP request POST and vary depending on the information that is entered as part of the checkout process on your shopping cart.

The parameter <code>$api_key</code> represents the API Key that is unique for every merchant. It should only change once the API key has been changed on the EPCarts side.

Having received the two parameters, the <code>EPCarts_sign</code> method will then perform an alphabetical sorting of the various key-value pairs based on the key but still maintaining the correlation between the keys and their respective values.

The method will then examine the <code>$query</code> variable for the various key-value pairs by checking for the <code>x_</code> prefix and would then append them together.

The method then computes the keyed hash value using the <code>hash_hmac</code> method.
