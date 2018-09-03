#Transact API Gateway Reference

##Authorisation Process

Where marked as such, data is mandatory and an error response may be received if not provided. Alternatively, the process may display a page to force the user to enter any missing data that is deemed mandatory for the completion of an authorization process.

The authorization process will not ask again for data that has already been provided.

##Resource Information

| Environment | URL |
|-------------|-----|
| Testing | [https://secure-sandbox.certegyezipay.com.au/](https://secure-sandbox.certegyezipay.com.au/)<br><br>The availability of this test environment is subject to change.<br>Please advise pit@certegy.com.au prior to testing. |
| Production | [https://secure.certegyezipay.com.au/](https://secure.certegyezipay.com.au/) |

#Resource Data Fields

##Request

| Key | Type | Required | Sample | Description &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |
|----------------------|--------------|------------|-----------------|---------------------------------------------------------------------|
| x_account_id | String | True | 30199999 | The merchant number provided to you by Certegy Ezi-Pay. |
| x_signature | String | True | | The signature for this request. See <a href="../../developer_resources/signature_generation/">Signature Generation</a> |
| x_guid | Guid (200) | False | | Your GUID reference for this transaction (required for resuming transactions) This is returned as part of the response |
| x_reference | String | False | ABC123 | Your reference for this transaction This is returned as part of the response |
| x_test | Boolean | False | True | Perform process under test mode<br>Default: False |
| x_staff_first_name | String | False | Harry | The first name of the staff member processing this transaction |
| x_staff_last_name | String | False | Tipper | The last name of the staff member processing this transaction |
| x_currency | ISO-4217 | False | AUD, NZD etc. | Will default to AUD if not specified |
| x_amount | Decimal | False | 1500.00 | The total sales amount of the transaction. |
| x_deposit_amount | Decimal | False | 100.00 | The deposit paid by the customer |
| product | String | | Diamond Ring | Short description of the item or service purchased. NOTE: This is excluded from the API signature process |
| x_vip_number | Long (10) | False | 1234567890 | The customer’s VIP or Pre-Approval number |
| x_customer_title | Integer | False | Mr = 1<br>Mrs = 2<br>Ms = 3<br>Miss = 4 | The customer’s title |
| x_customer_first_name | String | False | John | The customer’s first name |
| x_customer_middle_name | String | False | Andrew | The customer’s middle name (not initial). |
| x_customer_last_name | String | False | Smith | The customer’s surname |
| x_customer_email | String | False | it@certegy.com.au | The customer’s email address |
| x_customer_mobile_phone | String | False | 0400123123 | The customer’s mobile phone number |
| x_customer_home_phone | String | False | 0881231234 | The customer’s full home phone number |
| x_customer_dob | Date | False | 1980-12-01 | The customer’s date of birth in iso8601 standard date 2016-12-01. 18 years and older |
| x_customer_address_unit | String | False | 1 | The customer’s address (unit number) |
| x_customer_address_street_number | String | False | 97 | The customer’s address (street number) |
| x_customer_address_street_name | String | False | Pirie | The customer’s address (street name) |
| x_customer_address_street_type | String | False | Street | The customer’s address (street type) |
| x_customer_suburb | String | False | Adelaide | The customer’s address (suburb) |
| x_customer_state | String | False | ACT, NSW, QLD, SA, TAS, NT, VIC, WA | The customer’s address (state) |
| x_customer_postcode | Integer | False | 5000 | The customer’s address (postcode) |
| x_customer_country | String | False | AU, NZ etc. | Will default to AU if not specified |
| x_customer_employment_type | Integer | False | FullTime = 1<br>PartTime = 2<br>Casual = 3<br>SelfEmployed = 4<br>AgedPensioner = 5<br>VeteranPensioner = 6<br>SelfFundedRetiree = 7<br>NotEmployed = 8 | Employment type of the customer. |
| x_customer_employment_hours_per_week | Decimal | False | 38 | Customer's total working hours in a week (Not required for APC, VPC, SFR) |
| x_customer_employer_name | String | False | BHP Billiton | Customer's employer (Not required for APC, VPC, SFR) |
| x_customer_employer_suburb | String | False | Adelaide | Customer's employer suburb (Not required for APC, VPC, SFR) |
| x_customer_work_phone | String | False | 0882345678 | Customer’s work phone number (Not required for APC, VPC, SFR) |
| x_customer_abn | String | False | 99 888 888 888 | Customer's Australian Business Number (or ACN) Only If Self Employed |
| x_customer_last_pay_date | Date | False | 2018-05-01 | Customer’s last pay date For all Employment Types |
| x_customer_id_type | Integer | False | Driver’s License = 1<br>Age Pension Card = 3<br>Veteran Affairs Card = 4| Identity type provided by the customer |
| x_customer_id_state | String | False | SA | State where Customer's Identity issued (if applicable) |
| x_customer_id_expiry_date | Date | False | 2020-01-01 | Expiry date of Customer's Identity card (if applicable) |
| x_customer_id_number | String | False | abc255q | Identity card number |
| x_customer_id_reference | String | False | 123 | Additional identity card number/reference, i.e. NSW Drivers Licence Card Number |
| x_url_cancel | String (200) | False | https://example.com/Cancel | The location that the client is redirected to if the transaction is cancelled or an error occurs. |
| x_url_complete | String (200) | False | https://example.com/Complete | The location that the client is redirected to once the transaction is completed (Approved or Declined). |
| x_url_callback | String (200) | False | https://example.com/API | The location that our API will call as part of a background process for either outcome (Approved or declined) |

# Return Result

| Key | Type | Description |
|---------------------|------------|----------------------------------------------------------------------------------------------------------------------|
| x_account_id | String | Your Certegy Merchant number |
| x_purchase_number | String | Your purchase number for this transaction. |
| x_reference | String | Your originating reference for this transaction |
| x_guid | Guid | Your originating GUID reference for this transaction |
| x_test | Boolean | Test mode enabled flag |
| x_amount | Decimal | The purchase amount of the transaction |
| x_deposit | Decimal | The deposit amount required for this transaction. Note: This might be a higher amount than your initial deposit |
| x_timestamp | DateTime | System timestamp for the transaction |
| x_result | String | Response code from the transaction:<br>**Pending**<br>**Approved**<br>**Cancelled**<br>**Declined**<br>**Errors**<br>**Expired** |
| x_signature | String | Signature for this payload. Your application should verify this signature to ensure veracity of the response. See <a href="../../developer_resources/signature_generation/">Signature Generation</a>|