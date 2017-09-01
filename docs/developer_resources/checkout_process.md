# Checkout Process

Below is a chart that summarises the flow of a transaction when processing it using EPCarts.

<img src="/img/api/1.png" alt="EPCarts Checkout Process">

**NOTE:** We have included a sample cURL script that you can use to test the EPCarts sandbox endpoint. You can find the script under [Sample cURL Script](../developer_resources/sample_curl.md)

 **Step 1**: The customer places an order in a shopping cart providing details such as their first/last name, email address etc. The customer chooses EPCarts as the payment method.

 **Step 2**: The customer is redirected to the EPCarts checkout endpoint via a **HTTP POST** (See <a href="/developer_resources/api_reference/#Request">Request POST</a> for details). Note that this post needs to be signed to ensure security (See <a href="/developer_resources/signature_generation/">Signature Generation</a> for details).

 **Step 3**: The customer will then complete the purchase via the EPCarts Service. Customers that cancel will be redirected back to the <code>x_url_cancel</code> URL.

**Step 4**: Once a decision has been reached ('Approved' or 'Declined'), EPCarts will **POST** (Server to Server) to the provided <code>x_url_callback</code> URL  (See <a href="/developer_resources/api_reference/#Responses">Response POST</a> content).  

**Step 5**: The customer is then presented with an 'Approved' or 'Declined' page.  The customer is then redirected (**GET**) to the provided <code>x_url_complete</code> with the same <a href="/developer_resources/api_reference/#Responses">response</a> content as used in **Step 4**.  

 **Step 6**: The transaction is now complete from EPCarts side as well as the client's and shopping cart's point of views.
