# Sample cURL Script

Below is a sample cURL script that you can use to test the Oxipay test (sandbox) endpoint.

<hr>
<div style="font-family: monospace; font-size:1.2rem; color: #DC143C; word-wrap: break-word !important;">
curl 'https://securesandbox.%domain%/Checkout?platform=Default'  -H 'Content-Type: application/x-www-form-urlencoded' -X POST -d 'x_account_id=30199250&x_currency=AUD&x_amount=89&x_reference=9051364487&x_shop_country=AU&x_shop_name=Example+Store&x_transaction_type=&x_description=Tim%27s+Pet+Store&x_invoice=239051364487&x_test=true&x_customer_first_name=John&x_customer_last_name=Citizen&x_customer_email=john.citizen%40example.com&x_customer_billing_address1=some+address&x_customer_billing_address2=&x_customer_billing_city=Sydney&x_customer_billing_state=NSW&x_customer_billing_zip=2000&x_url_callback=http%3A%2F%2Fexample.com%2Fcallback.php&x_url_cancel=http%3A%2F%2Fexample.com%2Fcart.php&x_url_complete=http%3A%2F%2Fexample.com%2Fcomplete.php&x_signature=46017adf3644b9e1530f137009935a70aa0430b69750538de0878937c3eebe17'
</div>
<hr>
