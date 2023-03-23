---
title: Trades
---


|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|orders/getorders  | Get Order Details   |
| Post|orders/placeorder | To Place the Order  |
| Post|orders/modifyorder| To Modify the Order |
| Post|orders/deleteorder| To Delete the Order |



## Get Order

__Request Structure__ 

```
{
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'           |


__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": [
         {
            "cancelledQuantity": "0",
            "disclosedQuantity": 0,
            "exchange": "NSE",
            "uniqueID": null,
            "exchangeOrderId": "",
            "expiryDate": "-",
            "filledQuantity": 0,
            "instrumentName": "STARPAPER",
            "instrumentToken": "212",
            "instrumentType": "EQ",
            "isFNO": "N",
            "instrument": "EQ",
            "lastPrice": "",
            "leg": "1",
            "marketExchange": "NN",
            "marketLot": 1,
            "multiplier": "1",
            "netChange": 0,
            "optionType": "- ",
            "orderId": "2230228000506",
            "variety": "REGULAR",
            "orderQuantity": 1,
            "orderTimestamp": "Mar 01 2023 12:54:15:000PM",
            "pendingQuantity": 1,
            "pendingdiscQty": 0,
            "tradedQuantity": 0,
            "percentChange": "",
            "price": 150.0,
            "product": "NORMAL",
            "status": "NEWF",
            "statusInfo": "Confirmation Pending",
            "statusMessage": "Confirmation pending from Exchange",
            "strikePrice": 0,
            "tag": "MW",
            "strategyName": "",
            "transactionType": "BUY",
            "triggerPrice": 0,
            "validity": "-",
            "tradeSymbol": "",
            "name": "",
            "ordModTime": 0,
            "exchangeToken": 212
        },
    ]
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|cancelledQuantity	|String	|Quantity that's cancelled     |
|disclosedQuantity	|String	|Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie |
|exchange	|String	|Exchange (NSE or BSE or NFO or MCX) |
|uniqueID	|String	|The Unique ID for Orders |
|exchangeOrderId	|String	|Exchange generated order ID. Orders that don't reach the exchange have null IDs |
|filledQuantity	|String	|The Number of shares got filled |
|instrumentName	|String	|Script Name or Symbol |
|instrumentToken	|String	|The numerical identifier issued by the exchange represents the instrument. Used for subscribing to live market data over WebSocket |
|instrumentType	|String	|Instrument Type (EQ, FUT, CE, PE) |
|isFNO	|String	|Check Flag whether this order is Future and Options.  |
|instrument	|String	|The Exchange Segment. |
|lastPrice	|String	|Last price of the instrument at the time of placement |
|leg	|String	|Number of legs taken to place the order |
|marketExchange	|String	|The Market Exchange for NN |
|marketLot	|String	|The Lot size of the Scrip |
|multiplier	|String	|The Multiplier Of Scrip |
|netChange	|String	|The Net change of Scrip |
|optionType	|String	|There are four basic option types: buying a call option(BC), selling a call option(SC), buying a put option(BP), and selling a put option(SP).A call gives the buyer the right, to buy the underlying asset at the specified strike price. A put gives the buyer the right, to sell an asset at a specified strike price as in the contract. |
|orderId	|String	|Generated Unique Order ID to retrieve status or Modify |
|variety	|String	|Order variety (regular, amo, co etc.) |
|orderQuantity	|String	|Number of ordered quantity |
|orderTimestamp	|String	|Timestamp at which the order was registered by the API |
|pendingQuantity	|String	|Pending quantity to be filled |
|pendingdiscQty	|String	|Pending Disclosed quantity to be filled |
|tradedQuantity	|String	|traded Quantity to be filled |
|percentChange	|String	|Change percent of script |
|price	|String	|Price at which main leg of bracket order will be placed |
|product	|String	|Margin product to use for the order (margins are blocked based on this) ? |
|status	|String	|	Current status of the order. Most common values or COMPLETE, REJECTED, CANCELLED, and OPEN. There may be other values as well. |
|statusInfo	|String	|Order status |
|statusMessage	|String	|Textual description of the order's status. Failed orders come with human readable explanation |
|strikePrice	|String	|A strike price is a set price at which a derivative contract can be bought or sold when it is exercised. For call options, the strike price is where the security can be bought by the option holder; for put options, the strike price is the price at which the security can be sold. |
|strategyName	|String	|User's set Strategy Name or Order Tag |
|transactionType	|String	|BUY or SELL |
|triggerPrice	|String	|Trigger price (for SL, SL-M, CO orders) |
|validity	|String	|Order validity |
|tradeSymbol	|String	|Exchange tradingsymbol of the of the instrument |
|name	|String	|Name of the company (for equity instruments) |
|ordModTime	|String	|Ordered Date And Time ( DD/MM/YYYY HH:MM:SS) |
|exchangeToken	|String	|The numerical identifier issued by the exchange representing the instrument. |

## Place Order

__Request Structure__ 

```
{
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",
    "exchange": "NSE_EQ",
    "token": "212",
    "tradingSymbol": "SILVERMIC28FEB23",
    "qty": "1",
    "price": "150",
    "product": "NRML",
    "tranType": "BUY",
    "priceType": "L",
    "orderType": "NRML",
    "ret": "DAY",
    "triggerPrice": "",
    "disclosedQty": "",
    "MktProtection": "",
    "target": "",
    "stopLoss": "",
    "trailingStopLoss": "",
    "tag": "MW"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|vendor	|String	| The Broker Name eg., 'KOTAK' or 'INDIRA'          |
|exchange	|String	|Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)           |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details           |
|tradingSymbol	|String	|Exchange tradingsymbol of the of the instrument           |
|qty	|String	|Quantity to transact           |
|price	|String	|The price to execute the order at           |
|product	|String	|Product code (MIS or CNC or NRML)           |
|tranType	|String	|BUY or SELL           |
|priceType	|String	|PriceType (Limit , Market , SL , SL-M)           |
|orderType	|String	|Order type ( Regular , BO , CO , AMO)           |
|ret	|String	| Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type          |
|triggerPrice	|String	|The price at which an order should be triggered (SL, SL-M)           |
|disclosedQty	|String	|Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie           |
|MktProtection	|String	|A market-with-protection order cancels an order to buy or sell stock or other assets and re-submits it as a limit order. A broker might submit a market-with-protection order if the price of the stock has moved unexpectedly and dramatically since the market order was placed.           |
|target	|String	|Target Price is a limit that is the best possible outcome for the stockholder's investment.           |
|stopLoss	|String	|Stop Loss to minimise the loss in a trade           |
|trailingStopLoss	|String	| A trailing stop loss order adjusts the stop price at a fixed percent or number of points below or above the market price of a stock          |
|tag	|String	| An optional tag to apply to an order to identify it (alphanumeric, max 20 chars)          



__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": [
        {
            "Success": {
                "exchange": {
                    "orderId": "2230228000514",
                    "message": "Your Order has been Placed and Forwarded to the Exchange: 2230228000514.",
                    "price": 150.0,
                    "quantity": 1,
                    "tag": "1",
                    "exchange": "NSE_EQ"
                }
            }
        }
    ]
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-----------------------------|
|orderId	|String	|Generated Unique Order ID to retrieve status or Modify     |
|message	|String	|Order Request status i,e (Success or Failure) |
|price	|String	|The price to execute the order at    |
|quantity	|String	|Quantity ordered   |
|tag	|String	|An optional tag to apply to an order to identify it (alphanumeric, max 20 chars)      |
|exchange	|String	|Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)      |



## Modify Order

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",
    "exchange": "NSE",
    "token": "212",
    "tradingSymbol": "SILVERMIC28FEB23",
    "qty": "1",
    "price": "7",
    "product": "NRML",
    "tranType": "BUY",
    "priceType": "L",
    "orderType": "NRML",
    "ret": "DAY",
    "triggerPrice": "",
    "disclosedQty": "",
    "MktProtection": "",
    "target": "",
    "stopLoss": "",
    "trailingStopLoss": "",
    "tag": "MW",
    "orderNo":"2230228000514"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker          |
|vendor	|String	| The Broker Name eg., 'KOTAK' or 'INDIRA'          |
|exchange	|String	|Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)           |
|token	|String	| Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|tradingSymbol	|String	| Exchange tradingsymbol of the of the instrument          |
|qty	|String	|Quantity to transact           |
|price	|String	| The price to execute the order at          |
|product	|String	|Product code (MIS or CNC or NRML)           |
|tranType	|String	|BUY or SELL           |
|priceType	|String	|PriceType (Limit , Market , SL , SL-M)           |
|orderType	|String	| Order tye ( Regular , BO , CO , AMO)          |
|ret	|String	|  Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type         |
|triggerPrice	|String	|The price at which an order should be triggered (SL, SL-M)           |
|disclosedQty	|String	| Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie          |
|MktProtection	|String	| A market-with-protection order cancels an order to buy or sell stock or other assets and re-submits it as a limit order. A broker might submit a market-with-protection order if the price of the stock has moved unexpectedly and dramatically since the market order was placed.          |
|target	|String	|Target Price is a limit that is the best possible outcome for the stockholder's investment.           |
|stopLoss	|String	|Stop Loss to minimise the loss in a trade           |
|trailingStopLoss	|String	| A trailing stop loss order adjusts the stop price at a fixed percent or number of points below or above the market price of a stock          |
|tag	|String	|An optional tag to apply to an order to identify it (alphanumeric, max 20 chars)           |
|orderNo	|String	|Unique of number code is Order No          |




__Response Structure__

```
{
    "status": "Not ok",
    "message": "The Order has been Modify successfully",
    "result": [
        {
            "errorCode": 12,
            "message": ""
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|errorCode	 |String       | Error Code in Number       |
|message	 |String	    |Error Message)   |


## Delete Order

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",
    "product": "NRML",
    "orderNo":"2230228000514"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	 |String	| The unique, permanent user ID registered with the broker       |
|vendor	 |String	|    The Broker Name eg., 'KOTAK' or 'INDIRA'    |
|product |String	|Product code (MIS or CNC or NRML)        |
|orderNo |String	|Unique of number code is Order No        |




__Response Structure__

```
{
    "status": "Not ok",
    "message": "The Order has been Cancelled dify successfully",
    "result": [
        {
            "errorCode": 0,
            "message": ""
        }
    ]
}
```
 __Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|errorCode	 |String       | Error Code in Number       |
|message	 |String	    |Error Message)   |
