# API Documentation

This is a complete guide to the Oxipay API. The API allows you to quickly integrate Oxipay as a payment gateway into your choice of eCommerce solutions. We've already used this API to integrate Oxipay into a number of leading eCommerce solutions including Shopify, WooCommerce and Magento.

 

# API Documentation

Integrating Oxipay as a payment gateway into a shopping cart platform involves defining a translation layer that is specific to that platform.


##MapFrom()

The <code>MapFrom()</code> methods maps a request object from type IHttpRequest to type XpAuthRequest. The request object has two properties:

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

The method will initially attempt to verify the payload's signature and will also attempt to authenticate the request based on the merchant number that is being passed as well as the httpRequest. If it is unable to verify the payload's signature or unable to authenticate the request, then it will re-direct to a 401 error page with a *Signature Invalid* error message.

Otherwise it will post to the authorisation API. If there is an error in processing the authentication request, then it will re-direct the user to an error page that includes the code and a descriptive message corresponding to that particular error.

Additionally if the result of the post to the authorisation API is a valid result, then it will append an Oxipay specific transaction id to the URL, otherwise, it will append -1.

Note that the Oxipay transaction id is different to the transaction id that might be referenced in your shopping platform.

If an exception is thrown as a result of a failed authentication reuqest, then based on the result of the failed authentication request, will re-direct the user to a page that includes the code and a message of that particular failed authentication.

Also note that the <code>PostIndex()</code> method is an asynchronous method as specified by the method's <code>public async</code> return type.

## <code>GetIndex()</code> Method

Returns the current view.

## <code>ProcessInstore()</code> Method

The <code>ProcessInstore()</code> method will use the transaciton ID that is passed to it to return URL for processing an instore transaction - normally created from within the Oxipay merchant portal - as opposed to transactions created from within a shopping cart.

A transaction ID of <code>0</code> will result in an instance of the <code>HttpNotFoundResult</code> class being return with the message <code>Transaction Not Found</code>

The method does a post to the Authorisation API and if the result of the authorisation is an error that it will redirect to a page the includes the code of the error as well as a message relating to it.

Note that the method will throw an exception that redirects to a generic error page.

# Login

## Constructor Summary

**Constructor and Description**

<code>LoginController()</code>

## Method Summary

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
      <code>CheckToken()</code>
      <br>
      Verifies the validity of a token, returns an <code>Invalid Token</code> log warning message if the token is null or is white space.
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

