# P2P REST APIs

[Product Name] APIs use REST to manage your payments, and return HTTP response codes and responses encoded in [format].
You can use our REST APIs in Postman or using the command line.

...

## Recurring Payments

Call the Recurring Payments API to configure contact payment scheduling, review recurring payments,
and to modify or cancel recurring payments.


## Configure recurring payments

`POST /fintechp2p/{auth_id}/{contact_id}/recurring`

Add a recurring payment schedule to an existing contact on [product name]. Payments are automatically
scheduled to the contact for the period of time entered. 

You must have an authorized [product name] account and credentials to complete the recurring payment process.

### Request

**Path Parameters** 

* `auth-id` (required) - (string) Account authorization ID to for secure payment transactions using [product name].
* `contact-id` (required) - (string) The contact ID for the recurring payment. See `GET /fintechp2p/{auth_id}/contacts` for a full list of contact details.

**Header Parameters**

* `frequency` (Required) - (string) The cadence, or time unit in which to send payments. 
    * `day` for daily payments
    * `week` for weekly payments
    * `month` for monthly payments
* `start-date` (Required)- (string) The starting payment date in Internet data and time format.
* `end-date`-  The ending payment data in Internet data and time format. Leave this field blank for an unlimited automatic payment time.
* `amount` (Required)- (float) Payment value in USD. Value must be greater than 1.00

#### Request Sample

```json
{
   "amount":
   {
      "value": "70.50",
      "currency_code": "USD"
   },  
  "frequency": "month",
  "start-date": "2023-04-12T23:20:50.52Z",
  "end-date": ""
}
```

### Response

**200** a successful response the HTTP `200 OK` status code. This means the request was successful. A description of the result is 
shown in the message body.

#### Response Sample

```json
{
Sample 200 response  
}
```

## Review recurring payments

`GET /fintechp2p/{auth_id}/recurring`

Shows recurring payment details for all contacts with active recurring payment schedules.

**Path Parameters** 

* `auth-id` (required) - (string) Account authorization ID to for secure payment transactions using [product name].

### Response

**200** a successful response the HTTP `200 OK` status code, and a response body that shows each contact, and their recurring payment details.

#### Response Sample

```json
{
Sample 200 response  
  
}
```

## Modify recurring payments

`PATCH /fintechp2p/{auth_id}/{contact_id}/recurring`

Modify payment details for a contact's recurring payment schedule.

### Request


**Path Parameters** 

* `auth-id` (required) - (string) Account authorization ID to for secure payment transactions using [product name].
* `contact-id` (required) - (string) The contact ID for the recurring payment. See `GET /fintechp2p/{auth_id}/contacts` for a full list of contact details.

**Header Parameters**

* `frequency` (Required) - (string) The cadence, or time unit in which to send payments. 
    * `day` for daily payments
    * `week` for weekly payments
    * `month` for monthly payments
* `start-date` (Required)- (string) The starting payment date in Internet data and time format.
* `end-date` - The ending payment data in Internet data and time format. Leave this field blank for an unlimited automatic payment time.
* `amount` (Required)- (float) Payment value in USD. Value must be greater than 1.00.

#### Request Sample

```json
{
   "amount":
   {
      "value": "70.50",
      "currency_code": "USD"
   },  
  "frequency": "month",
  "start-date": "2023-04-12T23:20:50.52Z",
  "end-date": ""
}
```

### Response

**200** a successful response the HTTP `200 OK` status code. This means the request was successful. A description of the result is 
shown in the message body.

#### Response Sample

```json
{
  
 Sample 200 response  
 
}
```

## Cancel recurring payments

`DELETE /fintechp2p/{auth_id}/{contact_id}/recurring` 

Cancel the recurring payment schedule for a contact.

### Request


**Path Parameters** 

* `auth-id` (required) - (string) Account authorization ID to for secure payment transactions using [product name].
* `contact-id` (required) - (string) The contact ID for the recurring payment. See `GET /fintechp2p/{auth_id}/contacts` for a full list of contact details.

### Response

**200** a successful response the HTTP `200 OK` status code. This means the request was successful. Automatic recurring payments to that contact are immediately cancelled.


#### Response Sample

```json
{
Sample 200 response  
  
  
}
```

# Errors

...

# Technical Terms

...
