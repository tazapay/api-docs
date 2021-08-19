# Errors

The API uses the following error codes:

### HTTP Status Codes
Http Status Code | Meaning
---------------- | -------------------------------------------------------------------------------------------
400 	   	 | Bad Request		 : Your request is invalid
401        	 | Unauthorized		 : Your API key is wrong
403 	   	 | Forbidden 		 : The resource requested is not authorized
404 	  	 | Not Found  		 : The specified resource could not be found
405 	 	 | Method Not Allowed  	 : You tried to access with an invalid method
406 	   	 | Not Acceptable        : You requested a format that isn't json
410 	   	 | Gone 		 : The requested resource has been removed from our servers
429 	  	 | Too Many Requests  	 : You're requesting too many resources! Slow down!
500 	  	 | Internal Server Error : We had a problem with our server. Try again later
503 	  	 | Service Unavailable	 : We're temporarily offline for maintenance. Please try again later

## Tazapay Internal Error Codes
### generic
Error Code | Meaning
---------- | -------------------------------------------------------------------------------------------
1000	   | Failure on decoding the json request provided by the client
1001       | One of the queries for this operation has failed
1002       | Something went wrong with this API
1003       | Invalid parameter in the URL path.</br> Example : `/xyz/my_value/abc` Here `my_value` is invalid
1004       | Invalid parameter in the URL path.</br> Example : `/xyz/&sort=my_value/abc` Here `my_value` is invalid
1005       | The resource which you are trying to retrieve is not present

### auth
Error Code | Meaning
-----------|-----------------
1100       | Missing authentication header
1101       | Invalid access key
1102       | Unauthenticated api call

### session
Error Code | Meaning
-----------|-----------------
1200       | Invalid session
1201       | Session expired

### user
Error Code  | Description
------------|-------------
1300        | User email already exists but other fields are not synced to process the transaction
1301        | Failed to create user. please try again
1302        | Please provide the email address
1303        | Please provide `first_name` as account type is individual
1304        | Please provide `last_name` as account type is individual
1305        | Country is mandatory for account creation
1306        | Account type is mandatory for account creation
1307        | `business_name` is mandatory as account type is business
1308        | Please provide the password
1309        | Failed to set user password
1310        | Failed to update email verified as true
1311        | Failed to sign into the system

### escrow
Error Code  | Description
------------|-------------
1400        | Field is required
1401        | Value must be either `goods` or `service`
1402        | Field is required and must be a valid UUID
1403        | Alternate field is required or must be a valid UUID
1404        | Field is required and must be a valid email address
1405        | Field is required and must have ISO 3166-1 alpha-2 country code, Example: `IN`, `SG`
1406        | Field is required and must have ISO 4217 alpha-3 currency code, Example: `IND` `USA`
1407        | Field is required and value must be greater than 0
1408        | Value should be either `buyer` or `seller`
1409        | Value must be between 0 and 100
1410        | Alternate field is required or should have a dependent data
1411        | Please contact our support team to configure the defaults
1412        | User not found
1413        | Invoice currency is not supported at this moment
1414        | Please configure the default value or consider to pass a valid data in request
1415        | Invoice amount should be less than `%v` USD (dynamic value)
1416        | Invoice amount should be less than `%v` USD equivalent (dynamic value)
1417        | Country or invoice currency is not supported at this moment
1418        | Country or invoice currency is not supported at this moment
1419        | Field is required and value should be either individual or business
1420        | Counter party details not found

### payment
Error Code  | Description
------------|-------------
1500        | Error fetching `escrow_id` from database for corresponding `txn_no`
1501        | Error saving payment session in database
1502        | Field is required
1503        | Should be between 0 and 100

### metadata
Error Code  | Description
------------|-------------
1600        | Country is not supported at this moment
1601        | Currency is not supported at this moment
1602        | Amount should be greater than 0
1603	    | Amount should be less than %v USD (dynamic value)
1604        | Amount should be less than %v USD equivalent (dynamic value)
