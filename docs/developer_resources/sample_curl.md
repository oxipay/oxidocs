# Sample cURL Script

Below is a sample cURL script that you can use to test the Oxipay test (sandbox) endpoint.

<hr>
<div style="font-family: monospace; font-size:1.2rem; color: #DC143C; word-wrap: break-word !important;">
cURL -H "Content-Type: application/x-www-form-urlencoded" -X POST -d "x_reference=9051364487&x_account_id=1&x_amount=45.00&x_currency=AUD&x_url_callback=https%3A%2F%2Fcheckout.shopify.com%2Fservices%2Fping%2Fnotify_integration%2Ftimtestgw%2F13461757&x_url_complete=https%3A%2F%2Fcheckout.shopify.com%2F13461757%2Fcheckouts%2F95dde6450fe323cc9790cda0033a264b%2Foffsite_gateway_callback&x_shop_country=AU&x_shop_name=Tim%27s+Pet+Store&x_test=true&x_customer_first_name=Tim&x_customer_last_name=Atkinson&x_customer_email=dummy%40gmail.com&x_customer_billing_country=AU&x_customer_billing_city=Adelaide&x_customer_billing_address1=22+North&x_customer_billing_address2=Ave&x_customer_billing_state=SA&x_customer_billing_zip=5012&x_invoice=%239051364487&x_description=Tim%27s+Pet+Store+-+%239051364487&x_url_cancel=https%3A%2F%2Ftims-pet-store-2.myshopify.com%2Fcart&x_signature=f4423111c505e50a2dc7d9f988f2a446e1a39934c355fd0e7e3ffaf208bbade7" https://secure.oxipay.com.au/xpozsecure/Checkout?platform=shopify
</div>
<hr>


