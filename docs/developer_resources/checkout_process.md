# Checkout Process

Below is a chart that summarises the of a transaction when processing it using Oxipay.

<img src="/img/api/1.png" alt="Oxipay Checkout Process">

 **Step 1**: The customer places an order on the shopping cart and then provide required details such as their first and last name, email address amongst other things and then chose Oxipay as the method to process their transaction.

 **Step 2**: Once the customer's clicks on the button to process the payment with Oxipay, the are redirected to the Oxipay checkout URL. This is the Oxipay Endpoing which can be either the production or test endpoint depending on how you configured Oxipay for your particular shopping cart. The transaction details are **POST**ed in the <code>application/x-www-form-urlencoded</code> format. Note that this post will also include the x_signature key-value pair which is the hex-encoded value  of the various key-value pairs that represent this particular transaction.

 **Step 3**: Here, the customer would have landed on the Oxipay checkout page where they are prompted to login using their Oxipay credentials, if they are already registered, otherwise they can register for an Oxipay account. They will also be able to verify the details of their interest free payment plan that will be setup for this particular transaction and also enter their credit card details.

**Step 4**: Once the user clicks on **Submit** to process the transaction, the first thing that Oxipay does is perform a callback to the shopping cart using the endpoing that the shopping cart specified in the original POST request - <code>x_url_callback</code> key-value pair. This is to cater for scenarios where a customer - who has elected to process their payment using Oxipay - have their internet connection cut-off prematurely or their browser session killed accidently. This callback is also in in the <code>application/x-www-form-urlencoded</code>. Note, however, that customers can opt to exit the payment flow and cancel the Oxipay transaction altogether. In this case, they will be re-directed back to the <code>x_url_cancel</code>.

**Step 5**: Once Oxipay has finished processing the transaction - regardless of whether the outcome of processing is <code>completed</code>, <code>pending</code> or <code>failed</code> - it re-direct the user back to the shopping cart using the URL specified in the <code>x_url_complete</code> key-value pair as part of the original post request. The <code>x_url_complete</code> URL includes the various response values in the format <code>application/x-www-form-urlencoded</code> including <code>x_signature</code>. 

 **Step 6**: The transaction is complete here and the customer is re-directed to a <code>thank-you</code> page. Note that a lot of shopping carts implement the various pages that are part of the Oxipay flow - including the <code>thank-you</code> page for instance and as such developers wouldn't have to code them.
