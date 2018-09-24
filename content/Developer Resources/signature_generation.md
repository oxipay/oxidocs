---
title: "Signature Generation"
menuTitle: "Signature Generation"
date: 2018-05-17T12:13:55+09:30
draft: false
---


In order to prevent against malicious attacks and hijacking of browser sessions,  Oxipay implements a signing mechanism based on HMAC-SHA256. This section provides information on how you can use HMAC-SHA256 for signing and verification purposes.

As mentioned, Oxipay uses HMAC-SHA256 for purposes of signing and verifying requests.

Below is an example that demonstrates how you can go about implementing a method in a shopping platform that is based on PHP to generate the signature.

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


First note that the method expects two parameters and they are <code>$query</code> and <code>$api_key</code>. The <code>$query</code> represents the various key-value pairs that form your HTTP request POST and vary depending on the information that is entered as part of the checkout process on your shopping cart.

The parameter <code>$api_key</code> represents the API Key that is unique for every merchant. It should only change once the API key has been changed on the Oxipay side.

Having received the two parameters, the <code>oxipay_sign</code> method will then perform an alphabetical sorting of the various key-value pairs based on the key but still maintaining the correlation between the keys and their respective values.

The method will then examine the <code>$query</code> variable for the various key-value pairs by checking for the <code>x_</code> prefix and would then append them together.

The method then computes the keyed hash value using the <code>hash_hmac</code> method.




## Java Example 

```
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import javax.crypto.Mac;
import javax.crypto.spec.SecretKeySpec;
import java.security.InvalidKeyException;
import org.apache.commons.codec.binary.Hex;
import org.apache.commons.codec.binary.Base64;
import java.security.NoSuchAlgorithmException;
import java.io.UnsupportedEncodingException;
import java.nio.charset.Charset;
import java.util.HashMap;
import java.util.List;
import java.util.Set;

class Main
{
    private static final String _merchantId = "<insert your merchantId here>";
    private static final String _key = "<insert your key here>";
    private static final String _hashAlgorithm = "HmacSHA256";

    public static void main(String[] args) {
        
        HashMap<String, String>  map = new HashMap<String, String>();

        map.put("x_url_callback", "http://example.com/payments/oxipay/process");
        map.put("x_url_cancel", "http://example.com/payments/oxipay/cancel");
        map.put("x_url_complete", "http://example.com/payments/oxipay/process");
        map.put("x_account_id", _merchantId);
        map.put("x_amount", "400.00");
        map.put("x_currency", "AUD");
        map.put("x_reference", "TestOrder1");
        map.put("x_shop_country", "AU");
        map.put("x_shop_name", "Oxipay Mugs");
        map.put("x_test", "false");

        String plainText = signatureGeneration(_key, map);

        System.out.println("Plain Text: " + plainText);

        // generate the HMAC
        String hmac = signMessage(plainText, _key);

        System.out.println("HMAC " + hmac);
    }

    public static String signatureGeneration(String gatewayKey, HashMap apiArgs) {
        String[] stringArray = Arrays.copyOf(apiArgs.keySet().toArray(), apiArgs.size(), String[].class);
        List<String> keys = Arrays.asList(stringArray);

        // Sort the List
        try {
            Collections.sort(keys);
        } catch (Exception e) {
            System.out.print(e.getMessage());
        }

        String plainText = "";
        for(String key : keys){
            plainText += (key + apiArgs.get(key));
        }

        return  plainText;
    }

    private static String signMessage(String plainText, String key){
        String signature = "";
        try {
            Mac hmac = Mac.getInstance(_hashAlgorithm);
            SecretKeySpec secretKey = new SecretKeySpec(key.getBytes("UTF-8"), _hashAlgorithm);

            hmac.init(secretKey);
            signature = Hex.encodeHexString(hmac.doFinal(plainText.getBytes("UTF-8")));
            
        } catch (UnsupportedEncodingException e) {
            e.printStackTrace();
        } catch (InvalidKeyException e) {
            e.printStackTrace();
        } catch (NoSuchAlgorithmException e) {
             System.out.format("You do not have the %s libraries installed", _hashAlgorithm);
        }
        return signature;
    }
}

```

