### Test Credit Card Numbers

Due to PCI DSS compliance **only the following credit card numbers are able to be used in the secure test environment**, all other cards will result in a decline.

#### Accepted Numbers
|Type|PAN|Countries Available|AU Result|NZ Result|
|----|---|-------------------|---------|---------|
|**VISA**|**4242 4242 4242 4242**|**AU, NZ**|**Always approves**|**Always approves**|
|VISA|4111 1111 1111 1111|AU Only|Always approves|N/A|
|VISA|4564 8099 9999 9992|AU, NZ|Always approves|Dynamic _see below_|
|VISA|4564 4564 4564 4564|AU, NZ|Always approves|Dynamic _see below_|
|**MASTERCARD**|**5506 7500 0000 4364**|**AU, NZ**|**Always approves**|**Always approves**|
|MASTERCARD|5430 4899 9999 9992|AU, NZ|Always approves|Dynamic _see below_|
|MASTERCARD|5537 5010 1010 9112|AU, NZ|Always approves|Dynamic _see below_|

#### NZ CVV Values and Outcomes

NZ allows some cards to dynamically return different test results. The following CVV values can be used against NZ to force certain test outcomes.

|CVV Code|NZ Response Code|
|--------|-----------------|
|100|M (Matched)|
|200|N (Not Matched)|
|300|P (Not Processed)|
|400|S (Suspicious)|
|500|I (Issuer Not Registered)|
|Other number|U (Unsupported)|
