---
title: "Merchant Initiated Flow"
menuTitle: "Merchant Initiated Flow"
date: 2018-05-07T10:32:12+09:30
draft: false
weight: 1
---

<strong>API references: </strong>

 - <a href="/api/process_authorisation/">ProcessAuthorisation</a>
 - <a href="/api/invite/">Invite</a>

The merchant-initiated flow occurs when a customer arrives at the POI without a pre-approval code. Ideally, the customer would already have a pre-approval code as the customer-initiated flow is much more streamlined and synchronous*. Every effort should be made by ratailers to funnel customers to the <a href="/process/customer_initiated_flow/">customer-initiated</a> flow. These efforts might include the following:

* Oxipay tags on products that can be read by mobile devices (e.g. QR code) that take customers to the registration screen.
* Sales people driving customers to register before getting to the POI.

The merchant-initiated flow is a two step process. The first part involves the POS system brokering an Oxipay invite to the customer (by sending an SMS with a link to the registration screen). Once the customer has registered, the rest of the process is same as customer-initiated flow.

<div style="color: grey;">* by <b>synchronous</b> we mean the customer and merchant are on the same workflow. The merchant-initiated flow is <b>asynchronous</b> whereby the customer might be completing registration at the same time the merchant is tending to other POS transactions.</div><br/>


<strong>Step 1</strong>
![Oxipay Merchant Initiated Flow](/images/flows/cust-init-1.png)

---

<strong>Step 2</strong>

![Oxipay Customer Initiated Flow](/images/flows/cust-init-2.png)
