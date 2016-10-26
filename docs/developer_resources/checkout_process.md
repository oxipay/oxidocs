# Checkout Process

Below is a chart that summarises the flow of a transaction when processing it using Oxipay.

<img src="/img/api/1.png" alt="Oxipay Checkout Process">

**NOTE** We have included a sample cURL script that you can use to test the Oxipay sandbox endpoint. You can find the script under [Sample cURL Script](../developer_resources/sample_curl.md)

 **Step 1**: The customer places an order in a shopping cart providing details such as their first/last name, email address etc. During the checkout process, the customer will choose Oxipay as the payment method.

 **Step 2**: Once the customer clicks on the button to process the payment (with Oxipay), they will be redirected to the Oxipay checkout. The transaction details are **POST**ed through to Oxipay using the <code>application/x-www-form-urlencoded</code> format. Note that this post will also include the x_signature key-value pair which is the hex-encoded value of the various key-value pairs that represent this particular transaction.

 **Step 3**: Following the previous step, the customer will be prompted to login using their Oxipay credentials (if they are already registered, otherwise they can register for an Oxipay account). They will also be able to verify the details of their interest free payment plan and enter their credit card details.

**Step 4**: Once the user clicks on **Submit** to process the transaction; the first thing that Oxipay will do is perform an async HTTP POST back to the shopping cart using the endpoint specified by the <code>x_url_callback</code> in the original POST request. This is to cater for scenarios where a customer, has their internet connection cut-off prematurely or their browser or session killed accidently.

**Step 5**: Oxipay will then re-directs (via a HTTP POST) the user back to a confirmation page as specified by the <code>x_url_complete</code> key-value pair. The <code>x_url_complete</code> URL includes the various response values in the format <code>application/x-www-form-urlencoded</code> including <code>x_signature</code>

 **Step 6**: The transaction is now complete from Oxipay side as well as the client's and shopping cart's point of views.
