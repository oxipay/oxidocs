# Checkout Process

Below is a chart that summarises the flow of an Oxipay checkout process.

<img src="/img/api/1.png" alt="Oxipay Checkout Process">

1. The customer places an order on the shopping cart and then provide needed details such as email address, shipping and billing address. They will also choose Oxipay as they payment gateway method.

2. Once the customer has chosen to proceed with Oxipay, they are re-directed to the Oxipay checkout URL. This is done using a post request with the purchase details passed along in a query string format including the x_signature which represents the hex-encoded value of the key-value pairs that represent the order.

3. Once on the Oxipay payment gateway, the customer can verify the interest free payment plan that will be setup for this particular transaction and can also enter valid payment details in the form of a valid credit card number.

4. Here, customer have the option of proceeding with the processing the payment via Oxipay in which case they are re-directed back to the <code>x_url_complete</code> URL. The <code>x_url_complete</code> URL includes the various response values in the form of a URL encoded query string including <code>x_signature</code>. Note, however, that customers can opt to exit the payment flow and cancel the Oxipay transaction altogether. In this case, they will be re-directed back to the <code>x_url_cancel</code>.

5. There can be instances in which a customer elects to proceed with processing a payment using Oxipay but their connection might be cut-off prematurely. To accommodate for scenarios like this, Oxipay POSTs callbacks that are asynchronous to the URL specified in <code>x_url_callback</code>. Please note that these callbacks need to be in the HTTP POST x-www-form-urlencoded format.

6. The transaction is complete here and the customer is re-directed to a thank-you page. Note that a lot of shopping carts implement the various pages that are part of the Oxipay flow and as such they wouldn't need to be coded by developers.
