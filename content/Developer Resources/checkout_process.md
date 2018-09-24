---
title: "Checkout Process"
menuTitle: "Checkout Process"
date: 2018-05-17T12:13:55+09:30
draft: false
weight: 1
---


Below is a chart that summarises the flow of a transaction when processing it using Oxipay.

<img src="/images/api/1.png" alt="Oxipay Checkout Process">

**NOTE:** We have included a sample cURL script that you can use to test the Oxipay sandbox gateway. You can find the script under [Sample cURL Script](../developer_resources/sample_curl.md)

 **Step 1**: The customer places an order in a shopping cart providing details such as their first/last name, email address etc. The customer chooses Oxipay as the payment method.

 **Step 2**: The customer is redirected to the Oxipay checkout gateway via a **HTTP POST** (See <a href="/developer_resources/api_reference/#Request">Request POST</a> for details). Note that this post needs to be signed to ensure security (See <a href="/developer_resources/signature_generation/">Signature Generation</a> for details).

 **Step 3**: The customer will then complete the purchase via the Oxipay Service. Customers that cancel will be redirected back to the <code>x_url_cancel</code> URL.

**Step 4**: Once a decision has been reached ('Approved' or 'Declined'), Oxipay will **POST** (Server to Server) to the provided <code>x_url_callback</code> URL  (See <a href="/developer_resources/api_reference/#Responses">Response POST</a> content).  

**Step 5**: The customer is then presented with an 'Approved' or 'Declined' page.  The customer is then redirected (**GET**) to the provided <code>x_url_complete</code> with the same <a href="/developer_resources/api_reference/#Responses">response</a> content as used in **Step 4**.  

 **Step 6**: The transaction is now complete from Oxipay side as well as the client's and shopping cart's point of views.
