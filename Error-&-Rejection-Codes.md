# FIX API

## Order OrdRejReason Map
- The `OrdRejReason:103` is a field on a FIX execution report which provides details on the reasoning for the current state of the order.
- The `Text:58` is the textual description which explains the `OrdRejReason`.
- While the exact wording of the `Text:58` may change, `OrdRejReason` always refers to the same rejection reason in a general sense.
- For instance, the `OrdRejReason` 2009 will always refer to an invalid market symbol.

| OrdRejReason | Text |
| ---------- |---------------- |
| 1 | Unknown symbol |
| 5 | Unknown order |
| 6 |  Duplicate order |
| 13 | Incorrect quantity |
| 15 | Invalid account |
| 18 | Invalid price |
| 1001 | Ok |
| 1002 | Unable to place request  |
| 2001 | Bad incoming request |
| 2002 | Invalid user's client id |
| 2003 | Invalid handle |
| 2004 | Invalid quantity |
| 2005 | Unknown error  |
| 2006 | Invalid account type, account must be spot |
| 2007 | Account already exist  |
| 2008 | Invalid side, side must me from buy or sell  |
| 2009 | Invalid market |
| 2010 | Account doesn't exist  |
| 2011 | Account types are different  |
| 2012 | Invalid price  |
| 2013 | Invalid order type, type must be from limit, market, stop-limit  |
| 2015 | Exceeded maximum amount of allowed open margin orders  |
| 2016 | Unknown request type |
| 2017 | Invalid order id |
| 2018 | Unknown time in force option |
| 2020 | Margin trading is not allowed  |
| 2021 | Exceeded maximum amount of allowed open spot orders  |
| 2029 | Invalid request id |
| 2035 | Invalid nonce  |
| 3001 | Account doesn't have sufficient balance  |
| 3002 | Order is not found |
| 3003 | Borrowing is unavailable |
| 3007 | Duplicated order id  |
| 3020 | Unsolicited cancel |
| 3021 | Forced cancel  |
| 3023 | Duplicated order handle  |
| 3031 | Price is out of range  |
| 3032 | Order is either closed or rejected |
| 3064 | Incoming limit IOC, FOK or POST_ONLY failed to make or take |
| 6001 | Open |
| 6002 | Executed |
| 6003 | Matured  |
| 6004 | Expired  |
| 6005 | User cancelled |
| 6007 | Self cross prevention  |
| 6011 | Self cross prevention amend  |
| 6012 | Stop limit amend  |
| 6013 | Partially filled  |
| 6014 | Order accepted  |

# REST API

## Order statusReasonCode Map

- The `statusReasonCode` is a field on an Order which provides details on the reasoning for the current state of the order.
- The `statusReason` is the textual description which explains the `statusReasonCode`.
- While the exact wording of the `statusReason` may change, `statusReasonCode` always refers to the same `statusReason` in a general sense.
- For instance, the `statusReasonCode` 2009 will always refer to an invalid market symbol.

| statusReasonCode | statusReason |
| ---------- |---------------- |
| 1001 | Ok |
| 1002 | Unable to place request  |
| 2001 | Bad incoming request |
| 2002 | Invalid user's client id |
| 2003 | Invalid handle |
| 2004 | Invalid quantity |
| 2005 | Unknown error  |
| 2006 | Invalid account type, account must be spot |
| 2007 | Account already exist  |
| 2008 | Invalid side, side must me from buy or sell  |
| 2009 | Invalid market |
| 2010 | Account doesn't exist  |
| 2011 | Account types are different  |
| 2012 | Invalid price  |
| 2013 | Invalid order type, type must be from limit, market, stop-limit  |
| 2015 | Exceeded maximum amount of allowed open margin orders  |
| 2016 | Unknown request type |
| 2017 | Invalid order id |
| 2018 | Unknown time in force option |
| 2020 | Margin trading is not allowed  |
| 2021 | Exceeded maximum amount of allowed open spot orders  |
| 2029 | Invalid request id |
| 2035 | Invalid nonce  |
| 3001 | Account doesn't have sufficient balance  |
| 3002 | Order is not found |
| 3003 | Borrowing is unavailable |
| 3007 | Duplicated order id  |
| 3020 | Unsolicited cancel |
| 3021 | Forced cancel  |
| 3023 | Duplicated order handle  |
| 3031 | Price is out of range  |
| 3032 | Order is either closed or rejected |
| 3064 | Incoming limit IOC, FOK or POST_ONLY failed to make or take |
| 6001 | Open |
| 6002 | Executed |
| 6003 | Matured  |
| 6004 | Expired  |
| 6005 | User cancelled |
| 6007 | Self cross prevention  |
| 6011 | Self cross prevention amend  |
| 6012 | Stop limit amend  |
| 6013 | Partially filled  |
| 6014 | Order accepted  |

## Custody statusReasonCode Map

- The `statusReasonCode` is a field on Custody API's withdrawal and error messages which provides details on the reasoning for the current state of the request.
- The `statusReason` is the textual description which explains the `statusReasonCode`.
- While the exact wording of the `statusReason` may change, `statusReasonCode` always refers to the same `statusReason` in a general sense.
- For instance, the `statusReasonCode` 8305 will always refer to an assertion failure.

| statusReasonCode | statusReason |
| ---------- |---------------- |
| 8301 | Unexpected Error |
| 8305 | Withdraw assertion failed  |
| 8306 | Custody bad user  |
| 8307 | Unexpected withdraw exception  |
| 8310 | Cannot find withdrawal destination  |
| 8311 | Missing fields in withdraw  |
| 8313 | Unsupported coin  |
| 8315 | Crypto deposit not found  |
| 8316 | Unable to allocate deposit address  |
| 8317 | Swift code is on the restricted list  |
| 8318 | Unsupported operation  |
| 8319 | Custody operation has been disabled  |
| 8320 | Address failed validation  |
| 8322 | Bad withdrawal amount  |
| 8327 | Invalid Login  |
| 8329 | Unexpected destination exception  |
| 8331 | Invalid Destination  |
| 8332 | Bad network specified  |
| 8333 | Bad symbol specified |
| 8334 | Bad authentication type |
| 8335 | Withdrawal destination does not belong to user |
| 8336 | Withdrawal destination not whitelisted |
| 8399 | Unknown error |