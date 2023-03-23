---
title: Portfolio

---

# Portfolio

This API lets you retrieve holdings and positions in your portfolio.

|Method	|API                |Detail                         |
|-------|-------------------|-------------------------------|
|POST	| holdings/getUsrHold  |Retrieve the list of long term equity holdings|
|POST	| positions/getposition|Retrieve the list of short term positions|


## Holdings

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
|userId	|String	|The unique, permanent user ID registered with the broker        |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'        |


__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": [
        {
            "NSEToken": "101000438",
            "BSEToken": "201500103",
            "instrumentName": "BHEL",
            "qunatity": "45",
            "averagePrice": "110.00",
            "symbol": "BHEL",
            "isin": "INE257A01026",
            "instrument": "EQ",
            "Close": "70.34",
            "holdingCost": 4950,
            "lastPrice": "71.40",
            "LotSize": "1",
            "unrealisedGainLoss": "-1737.00"
        }
    ]
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|NSEToken	|String	|    Token of the scrip. Token Number is a unique code given to all companies listed on the NSE exchange. Selected Instrument token number will be displayed under scrip details       |
|BSEToken	|String	| Token of the scrip. Token Number is a unique code given to all companies listed on the BSE exchange. Selected Instrument token number will be displayed under scrip details          |
|instrumentName	|String	| Script Name or Symbol          |
|qunatity	|String	| Net quantity (T+1 + realised)          |
|averagePrice	|String	|  Price at which the quantity was filled         |
|symbol	|String	| Exchange symbol of the of the instrument          |
|isin	|String	|  The standard ISIN representing stocks listed on multiple exchanges         |
|instrument	|String	|The Exchange Segment.           |
|Close	|String	| Closing price of the instrument from the last trading day          |
|holdingCost	|String	|Average Price of the Script           |
|lastPrice	|String	| Last traded market price of the instrument          |
|LotSize	|String	| Quantity of a single lot          |
|unrealisedGainLoss	|String	|The Unrealised Profit and Loss calculated with last traded market price of the instrument           |



## Positions

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
|userId	|String	|The unique, permanent user ID registered with the broker        |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'        |



__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": [
        {
            "exchange": "NSE",
            "exchangeToken": "212",
            "symbol": "STARPAPER",
            "assetType": "",
            "tradeSymbol": "STARPAPER-EQ",
            "segment": "EQ",
            "token": 212,
            "preNetQty": 0,
            "netQty": 0,
            "TotalNetQty": 0,
            "SquareOff": 0,
            "ProductType": "",
            "netPrice": "0",
            "ltp": "172",
            "mtm": "",
            "lotSize": "",
            "instrument": "STARPAPER-EQ",
            "buyAmt": "300.0",
            "sellAmt": "0",
            "buyQty": 0,
            "sellQty": 0,
            "Expiry": "-",
            "strike_price": "0",
            "option_Type": "- "
        }
    ]
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|exchange	|String	|Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)           |
|exchangeToken	|String	|The numerical identifier issued by the exchange representing the instrument.           |
|assetType	|String	|The type of asset           |
|tradeSymbol	|String	|Exchange tradingsymbol of the of the instrument           |
|segment	|String	|Segment is ( EQ , FUT , PE , CE )           |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details           |
|preNetQty	|String	|Pre Net Quantity of the position           |
|netQty	|String	| Net Quantity of the position          |
|TotalNetQty	|String	| Total Net Quantity of position          |
|SquareOff	|String	|reverse order of the script           |
|ProductType	|String	|Price type(L or MKT or SL or SL-M)           |
|netPrice	|String	|The Net price is the value at which a product or service is sold after all taxes and other costs are added and all discounts subtracted.           |
|ltp	|String	|Last trade price of the scrip. The price at which the final trade happens between a buyer and a seller           |
|mtm	|String	| Mark to market returns (computed based on the last close and the last traded price).Mark to market (MTM) is a method of measuring the fair value of accounts that can fluctuate over time, such as assets and liabilities. Mark to market aims to provide a realistic appraisal of an institution's or company's current financial situation based on current market conditions.          |
|lotSize	|String	|Quantity of a single lot           |
|instrument	|String	|The Exchange Segment.           |
|buyAmt	|String	| The net price is the value at which a product or service is sold after all taxes and other costs are added and all discounts subtracted.          |
|sellAmt	|String	|The net price is the value at which a product or service is sold after all taxes and other costs are added and all discounts subtracted.           |
|buyQty	|String	| Position Buy Quantity          |
|sellQty	|String	|Position Sell Quantity           |
|Expiry	|String	| Stock's Expiry date will be displayed.An expiry date in trading is the point at which a position automatically closes. In other words, a trader will have to decide what they want to do with their open position before the expiry date.          |
|strike_price	|String	| A strike price is a set price at which a derivative contract can be bought or sold when it is exercised. For call options, the strike price is where the security can be bought by the option holder; for put options, the strike price is the price at which the security can be sold.          |
|option_Type	|String	| There are four basic option types: buying a call option(BC), selling a call option(SC), buying a put option(BP), and selling a put option(SP).A call gives the buyer the right, to buy the underlying asset at the specified strike price. A put gives the buyer the right, to sell an asset at a specified strike price as in the contract.          |


