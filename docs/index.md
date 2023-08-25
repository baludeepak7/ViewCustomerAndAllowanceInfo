**ViewCustomerAndAllowanceInfo**

Service Description
===================

This API will return the customer details and their account current allowances.

Request
-------

MSISDN (String) -> Customer MSISDN e.g. 447874384949

Response
--------

Response will contain **Customer** and **Allowance** objects.

Customer 
--------                           

  firstName (String) -> First name of primary contact. This can be obtained from “Primary Contact” object from REST backend API response

  lastName (String) ->  Last name of primary contact. This can be obtained from “Primary Contact” object from REST backend API response

  middleName (String) -> Middle name of primary contact. This can be obtained from “Primary Contact” object from REST backend API response

  title (String) -> Title of primary contact. This can be obtained from “Primary Contact” object from REST backend API response 
  
------------------------------------------------------------------------------------------------------------

Allowance 
---------

  Parameter            Data Type   Description
  -------------------- ----------- ----------------------------------------
  freeUnitType         String      Free unit type.
  freeUnitTypeName     String      Free unit type name.
  measureUnit          String      Measurement unit ID for a free unit.
  measureUnitName      String      Measurement unit name for a free unit.
  totalInitialAmount   Long        Initial value for a free unit.
  totalUnusedAmount    Long        Current value for a free unit.

It should be noted that the above structure will be repeated for each
allowance type (voice, text & data unit instances). The above data can
be obtained from “FreeUnitItem” section of SOAP backend API response.

Error response
--------------

  Parameter          Data Type   Description
  ------------------ ----------- ------------------------------------------------------------------------
  error              String      Error code
  errorDescription   String      Error description.
  additionalInfo     String      Any additional info about the root cause of the error from the backend
