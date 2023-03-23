---

title: Trades

---


|Method	     |API   	|Detail             |
|------------|----------|------------------ |
| Post|trades/gettrades | Get Trade Details  |

## Trades

__Request Structure__ 

```
{
    "userId": "<USER_ID>",
    "vendor": "<VENDOR_NAME>",
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|vendor	|String	|The Broker Name eg., 'KOTAK' or 'INDIRA'           |


__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": []
}
```

<!-- __parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------| -->
 
 