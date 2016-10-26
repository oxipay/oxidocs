# Checkout Process

Below is a chart that summarises the of a transaction when processing it using Oxipay.

<img src="/img/api/1.png" alt="Oxipay Checkout Process">

**NOTE** Please note that we have included a sample cURL script that you can use to test the Oxipay test (sandbox) endpoint. You can find the script under [Sample cURL Script](../developer_resources/sample_curl.md)

 **Step 1**: The customer places an order on the shopping cart and then provide required details such as their first and last name, email address amongst other things and then chose Oxipay as the method to process their transaction.

 **Step 2**: Once the customer's clicks on the button to process the payment with Oxipay, the are redirected to the Oxipay checkout URL. This is the Oxipay Endpoing which can be either the production or test endpoint depending on how you configured Oxipay for your particular shopping cart. The transaction details are **POST**ed in the <code>application/x-www-form-urlencoded</code> format. Note that this post will also include the x_signature key-value pair which is the hex-encoded value  of the various key-value pairs that represent this particular transaction.

 **Step 3**: Here, the customer would have landed on the Oxipay checkout page where they are prompted to login using their Oxipay credentials, if they are already registered, otherwise they can register for an Oxipay account. They will also be able to verify the details of their interest free payment plan that will be setup for this particular transaction and also enter their credit card details.

**Step 4**: Once the user clicks on **Submit** to process the transaction and Oxipay has processed the transaction, the first thing that Oxipay does is perform a POST callback to the shopping cart using the endpoing that the shopping cart specified in the original POST request - <code>x_url_callback</code>. This is to cater for scenarios where a customer - who has elected to process their payment using Oxipay - have their internet connection cut-off prematurely or their browser session killed accidently. This callback is also in in the <code>application/x-www-form-urlencoded</code>. 

**Step 5**: Secondly, Oxipay will send a GET to the client that re-directs the user back to a thank you page as specified in the <code>x_url_complete</code> key-value pair or re-directs them to an order cancelled page as specified in <code>x_url_cancel</code> if they have decided to cancel their transaction whilst on the Oxipay checkout page. The <code>x_url_complete</code> URL includes the various response values in the format <code>application/x-www-form-urlencoded</code> including <code>x_signature</code>

 **Step 6**: The transaction is now complete from Oxipay side as well as the client's and shopping cart's point of views.
