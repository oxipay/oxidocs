#Overview

This API document is intended for use by %product_name%’s merchants who wish to move to a partially integrated authorisation process. The API is generic in nature, and is designed to enable a flexible approach to capture the data relevant to a Certegy Ezi-Pay contract.

##How It Works

The client’s browser performs the post to Certegy’s API. The POST endpoint returns a view. This view is essentially a UI to complete the final payment step (and resolve any validation errors from the posted data).

A typical implementation of this payment integration will require server side application to return an html page to the client containing the payload data (as hidden fields, including the signature) and the target URL. As a suggestion, the webpage you build could automatically redirect the client’s browser to Certegy’s server so they can complete the payment information step. Perhaps this page can have “redirecting to %product_name%...” text so they can see this hand over to Certegy. When this hand over to Certegy occurs, the API takes control and will request any remaining information that is required to complete the authorisation.

<img src="/img/api/2.png" alt="Transact flow">

Once the client has been passed to us, we will validate the data and prepopulate any data fields in a standard ’10-3’ authorisation flow.

An approved, declined, error page may follow an authorisation. **These pages do not redirect automatically.** The page relies on the client to press the ‘Redirect Now’ button. This action will redirect to the URLs you provided in the original POST.
