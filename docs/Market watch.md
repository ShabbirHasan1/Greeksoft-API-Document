---
title: Market Watch

---


The Market Watch services is used to retrieve watchlist of a particular User. All valid instruments can be added to the Market Watch. The count of the Market Watch and total number of scrips per market watch is configurable during the installation of the middleware.

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|marketWatch/createMW|Create marketWatch| 
| Post|marketWatch/getAllMwScrips |Get all Market Watch & scrips from Market Watch.|
| Post|marketWatch/getMWScrips |get market watch scripsrequest.|
| Post|marketWatch/renameMW|Rename Market Watch| 
| Post|marketWatch/sortMwScrip|Sort scrips in Market Watch.| 
| Post|marketWatch/addscrip |Add Scrip to the Market Watch.|
| Post|marketWatch/deletescrip | Delete Scrip from Market Watch.|


### Create MarketWatch

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
|vendor	|String	| The Broker Name eg., 'KOTAK' or 'INDIRA'       |


__Response Structure__

```
{
    "stat": "Not ok",
    "message": "You have reached the maximum length of Match watch",
    "result": null
}
```
<!-- __Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Exchange        |
|mwName	 |String	    |Trading Segment  |
|scrips       |ArrayList	    |Refer Unique token from exchange    | -->

###  Get All MarketWatch

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
    "message": "Null",
    "result": [
         {
            "mwId": "1",
            "vendor": "<VENDOR_NAME>",,
            "mwName": "MWList1",
            "scrips": null
        },
        {
            "mwId": "2",
            "vendor": "<VENDOR_NAME>",,
            "mwName": "KOTAK",
            "scrips": [
                {
                    "scripName": "INFIBEAM-EQ",
                    "exchange": "NSE",
                    "segment": "nse_cm",
                    "token": "16249",
                    "tradingSymbol": "INFIBEAM-EQ",
                    "expiry": null,
                    "sortOrder": 1,
                    "pdc": "0"
                }
            ]
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Unique market watch ID        |
|vendor	 |String       |The Broker Name eg., 'KOTAK' or 'INDIRA'        |
|mwName	 |String	    |Unique market watch Name  |
|scrips  |String	    |List of scripts in market watch    |
|scripName  |String	    |The Name of script    |
|exchange  |String	    |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)    |
|token  |String	    |  Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details  |
|tradingSymbol  |String	    |Exchange tradingsymbol of the of the instrument    |
|expiry  |String	    |Expiry date (for derivatives)    |
|sortOrder  |String	    |order of script in list    |
|pdc  |String	    |Previce Day Close Value    |





###  Get MarketWatch 

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "mwId":"3",
    "vendor": "<VENDOR_NAME>",
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker        |
|mwId	 |String       |Unique market watch ID        |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'        |





__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
       {
            "scripName": "ASHOKLEY-EQ",
            "exchange": "NSE",
            "segment": "nse_cm",
            "token": "212",
            "tradingSymbol": "ASHOKLEY-EQ",
            "expiry": null,
            "sortOrder": 1,
            "pdc": "0"
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|scripName	 |String       |The Name of script        |
|exchange	 |String	    |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)  |
|segment       |String	    |Segment the instrument belongs to           |
|token |String  |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details|
|tradingSymbol    	 |Date	    |Exchange tradingsymbol of the of the instrument        |
|expiry   |String	    |  Expiry date (for derivatives)        |
|sortOrder    |Int	    |order of script in list        |
|pdc    	 |String	    |Previce Day Close Value  |

### Rename MarketWatch

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "mwId": "2",
    "mwName": "KOTAK",
    "vendor": "<VENDOR_NAME>",
}
```
__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker          | 
|mwId	|Int	|Unique market watch ID          | 
|mwName	|String	|Unique market watch Name           | 
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'           | 


__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": []
}

```

### Sort MarketWatch

__Request Structure__


```
{
    "mwId": "1",
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",,
    "scripData": [
        {
            "exch": "NSE",
            "token": "6833",
            "sortingOrder": 2
        },
        {
            "exch": "NSE",
            "token": "212",
            "sortingOrder": 1
        }
    ]
}
```
__Input parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Unique market watch ID        |
|userId       |String	    |The unique, permanent user ID registered with the broker           |
|vendor       |String	    | The Broker Name eg., 'KOTAK' or 'INDIRA'          |
|scripData |String  |List of scripts data               |
|exch    	 |String	    |Exchange (NSE or BSE or NFO or MCX)          |
|token   |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|sortingOrder    	 |Int	    |order of script in list          |
|exch    	 |String	    |Exchange (NSE or BSE or NFO or MCX)          |
|token|String   |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details         |
|sortingOrder| Int |order of script in list |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": Null
}
```




### Add Instrument

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "mwId": "2",
    "vendor": "<VENDOR_NAME>",,
    "scripData": [
        {
            "exch": "NSE",
            "token": "16249"
        }
    ]
}

```
__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker   |
|mwId	|String	|Unique market watch ID   |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'   |
|exch	|String	|Exchange (NSE or BSE or NFO or MCX)    |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details     |


__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
          {
            "scripName": "INFIBEAM-EQ",
            "exchange": "NSE",
            "segment": "nse_cm",
            "token": "16249",
            "tradingSymbol": "INFIBEAM-EQ",
            "expiry": null,
            "sortOrder": 2,
            "pdc": "0"
        }
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|scripName    	 |String	    |The Name of script |
|exchange	 |String       |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)        |
|segment	 |String	    |Segment the instrument belongs to |
|token       |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details      |
|tradingSymbol |Equity  |Exchange tradingsymbol of the of the instrument |
|expiry    	 |String	    |Expiry date (for derivatives)       |
|sortOrder   |Int	    |order of script in list |
|pdc    	 |String	    |Previce Day Close Value  |

### Delete Instrument

__Request Structure__


```
{
    "userId": "<USER_ID>",
    "mwId": "4",
    "vendor": "<VENDOR_NAME>",,
    "scripData": [
        {
            "exch": "NSE",
            "token": "212"
        }
    ]
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker   |
|mwId	|String	|Unique market watch ID   |
|exch	|String	|Exchange (NSE or BSE or NFO or MCX)    |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details      |

__Response Structure__


```
{
    "status": "Ok",
    "message": "Success",
    "result": []
}
```
<!-- __Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|status	 |String       |Equity Cash        |
|data	 |String	    |Futures & Options  | -->