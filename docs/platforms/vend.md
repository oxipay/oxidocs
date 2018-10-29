<h1>Setup on Vend</h1>

To setup and configure Oxipay with your Vend POS device you will need the following:


<div class="panel">
 <ul>
    <li>Your Merchant ID</li>
    <li>A POS Device Token for each Vend Device</li>
 </ul>
</div>

Device Tokens can be generated in your <a href="https://portals.%domain%/merchantarea#/login">Oxipay Merchant Portal</a>

1. Login to the <a href="https://portals.%domain%/merchantarea#/login">Oxipay Merchant Portal</a>

2. Select the menu in the top right corner

3. Select POS Device Tokens

4. Select "Generate" and provide the number of registers you have allocated in Vend
<hr/>

## Setup Process

### Add a payment type

Login to your Vend store.
Go to Settings -> Payment Types -> Add Payment Type


![01_add_payment_type.png](/img/platforms/vend/01_add_payment_type.png)

---

### Create new "Credit Card" Payment Type

Select:

* Payment Type =  Credit Card
* Custom Name = Oxipay


![02_select_credit_card.png](/img/platforms/vend/02_select_credit_card.png)


![03_name_oxipay.png](/img/platforms/vend/03_name_oxipay.png)

---

### Configure Oxipay Payment Type

On the Settings -> Payment Types screen, choose the Oxipay Payment Type


![04_configure_oxipay.png](/img/platforms/vend/04_configure_oxipay.png)



Set the Gateway URL to:

```https://vend.%domain% ```

Press the "Save Pament Type"

![05_add_custom_gateway.png](/img/platforms/vend/05_add_custom_gateway.png)

---
### Pair a Register

Oxipay requires each Vend register to be paired with Oxipay before it can transact against the Oxipay POS endpoint.

In order to do this, you simply need to perform a test transaction from each Vend Register with-in your store.

You will be prompted for your:

* **Merchant ID**
* **Device Token.**

Your **Merchant ID** is provided in your Welcome Pack.

**Device Tokens** can be generated in the <a href="https://portals.%domain%/merchantarea#/login">Oxipay Merchant Portal</a>



![06_payment.png](/img/platforms/vend/06_payment.png)

![07_pay_with_oxipay.png](/img/platforms/vend/07_pay_with_oxipay.png)

![08_pair_register.png](/img/platforms/vend/08_pair_register.png)

---

## Complete

Congratulations! Once a register is paired, your customers can now pay with Oxipay
