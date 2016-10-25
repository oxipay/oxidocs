## <code>MapFrom()</code> Method

As its name implies, the <code>MapFrom()</code> methods maps a request object that is passed to it from the shopping cart from the <code>IHttpRequest</code> format into the <code>XpAuthRequest</code>.

The <code>IHttpRequest</code> request object that is passed to the <code>MapFrom()</code> method represents the transaction payload that contains the various transaction specific details such as the transaction amount, a customer's biling country and the shop's name (merchant's name as advertised on the internet and other media).

Below is a table that summarises the various information that the translation layer expects to be within the request:

Variable                      | Description
-------------------           | -----------
x_currency                    | Currency in which the transaction was processed, typically AUD.
x_url_complete                | URL that users are re-directed to when a transaciton has processed successfully.
x_url_callback                | Callback URL that is re-directed after the API method has been called
x_url_cancel                  | URL that users are re-directed to when they cancel a transaction.
**Merchant Specific**
x_shop_name                   | The merchant's or business' name as advertised on the Internet, TV and other media
x_account_id                  | The merchant's ID, this is unique to every merchant
x_reference                   | Rerference for that particular transaction
x_invoice                     | Transaction's invoice
**Order Specific**
x_amount                      | Total amount for that transaction including any shipping costs and taxes such as GST
**Customer Specific**
x_customer_first_name         | Customer's first name
x_customer_last_name          | Customer's last name
x_customer_email              | Customer's email address
x_customer_phone              | Customer's phone number (could also be their mobile)
x_customer_billing_address1   | Customer's billing address - line 1
x_customer_billing_address2   | Customer's billing address - line 2
x_customer_billing_city       | Customer's billing city
x_customer_billing_state      | Customer's billing state
x_customer_billing_zip        | Customer's billing zip code
x_customer_billing_address1   | Customer's billing address - line 1
x_customer_billing_address2   | Customer's billing address - line 2
x_customer_billing_city       | Customer's billing city
x_customer_billing_state      | Customer's billing state
x_customer_billing_zip        | Customer's billing zip code
x_customer_shipping_address1  | Customer's shipping address - line 1
x_customer_shipping_address2  | Customer's shipping address - line 2
x_customer_shipping_city      | Customer's shipping city
x_customer_shipping_state     | Customer's shipping state
x_customer_shipping_zip       | Customer's shipping zip code
**Gateway Specific**
x_test                        | A flag that indicates whether the transaction is to be processed as a live transaction or as a test transaction. No actual dollar amounts are debitted when the test flag is enabled.



* An input stream of type <code>Stream</code>
* A query string that is a name value collection, type <code>NameValueCollection</code>

<table class="table table-striped table-hover ">
  <thead>
    <tr>
      <th>Modifier</th>
      <th>Method and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>public</code></td>
      <td>
      <code>MapFrom()</code>
      <br>
      Maps a request from type <code>IHttpRequest</code> to type <code>XpAuthRequest</code>.
      </td>
    </tr>
    <tr>
      <td><code>public</code></td>
      <td><code>Logout</code>
      <br>
      Processes a log out request of type <code>LougoutRequest</code>. Returns an <code>Invalid Logout Request</code> if the log out request is null, whitespace or is the default value.</td>
      </td>
    </tr>
  </tbody>
</table>

# Checkout Controller

## <code>PostIndex()</code> Method


Modifier and Type                                 | Method Signature
--------------------                              | -----------------
<code>public async Task < ActionResult ></code>   | <code>PostIndex()</code>

The <code>PostIndex()</code> method returns an Oxipay specific checkout URL to which the shopping cart can post the transaction to. It is a public asynchronous method as specified by the method's <code>public async</code> modifier and type.

For the <code>PostIndex()</code> method to return a valid checkout URL, the shopping cart's platform would need to be authenticated successfully based on the calling platform's authentication rules. This involves successfully verifying the signature as well as the merchant number that is being passed and the <code>httpRequest</code> itself.

Failure to successfully authenticate  the request will result in being re-directed to a <code>401</code> error page with a <code>Signature Invalid</code> message.

Also note that Oxipay might re-direct to an error page if the request was authenticated but was not authorised after being posted to the Authorisation API. The error page will include both a code and a description message for that particular failed authorisaiton.

If an exception occurs, then the method will also re-direct to an error page that includes a code and a message for that particular error.

## <code>GetIndex()</code> Method

Returns the current view.

## <code>ProcessInstore()</code> Method

The <code>ProcessInstore()</code> method will use the transaciton ID that is passed to it to return URL for processing an instore transaction - normally created from within the Oxipay merchant portal - as opposed to transactions created from within a shopping cart.

A transaction ID of <code>0</code> will result in an instance of the <code>HttpNotFoundResult</code> class being return with the message <code>Transaction Not Found</code>

The method does a post to the Authorisation API and if the result of the authorisation is an error that it will redirect to a page the includes the code of the error as well as a message relating to it.

Note that the method will throw an exception that redirects to a generic error page.