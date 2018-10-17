---
title: "Signature Generation"
menuTitle: "Signature Generation"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<h3>Signature generation</h3>

All Oxipay APIs are publicly accessible. In order to prevent against request-tampering, man-in-the-middle attacks, and other malicious behavior, Oxipay requires all API requests to include a digital signature and will include a digital signature on all API responses.

For all API requests to Oxipay, the digital signature ***will*** be verified. Responses ***should always*** be verified on the POS side before continuing.

The signing mechanism used by Oxipay is based on <a href="https://en.wikipedia.org/wiki/Hash-based_message_authentication_code">HMAC-SHA256</a>. Every individual device that communicates with Oxipay must use its cryptographic signing-key known as the 'device-signing-key' to generate the HMAC (hash-based message authentication code). The device-signing-key is installed securely during the one-time 'device initialisation' operation.

To generate a digital signature, do the following steps:

1. Create a string of all "x_" fields (i.e. with a name starting with "x_") in the request as key-value pairs, sorted alphabetically, and concatenated without separators.
2. Sign the message using HMAC_SHA256 to produce a signature.

Add the 'signature' to the request and that's it!

On the Oxipay side, we'll perform the same algorithm with the same device-signing-key for the HMAC_SHA256 to produce a matching signature. If anything changes on the request, even just a single character, then a completely different signature would be generated. A non-matching signature would result in an authorisation error.

Below is a C#.NET code snippet that demonstrates how a signature might be generated:

```cs
public static string GenerateHMAC(string apiKey, IDictionary<string,string> payloadValues)
{
  using (var hmac = new HMACSHA256(Encoding.UTF8.GetBytes(apiKey)))
  {
      string payloadSignature = 
        payloadValues
          .Where(kvp=> kvp.Key.StartsWith("x_"))
          .OrderBy(kvp=>kvp.Key)
          .Select(kvp => $"{kvp.Key}{kvp.Value}")
          .Aggregate((current, next) => $"{current}{next}");

      var rawHmac = hmac.ComputeHash(Encoding.UTF8.GetBytes(payloadSignature));

      return BitConverter.ToString(rawHmac).Replace("-", string.Empty).ToLower();
  }
}
```
