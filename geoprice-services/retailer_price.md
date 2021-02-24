# Retailer Price and Stock -API


```

['date', 'price', 'original_price', 'stock', 'promotion', 'url', 'info']

* date (str) "20200413" , format - YYYYMMDD , must
* price (str) 34.55 , must be 2 decimal places, only digits or "." , must 
* original_price (str) 40.00 , must be 2 decimal places , only digits or "." , must , pass same as price if not possible
* stock (str) , # -1 out_of_stock, 0 means available, more than 0 means we have real_stock option , must
* promotion (str) , optional, pass empty string.
* url (str), optional, pass empty string.
* info (str), optional, any additional info you want to pass, pass empty string.

```


### Update Price - For third party

#### Request - All OK

```
POST /geoprice/retailer_price/update?retailer_key=walmart&retailer_product_id=test1&retailer_store_id=walmart1 HTTP/1.1
Host: 127.0.0.1:5000
X-api-key: client_key
Content-Type: application/json

{
	"date": "20200420",
	"price": "20.50",
	"original_price": "30.99",
	"stock": "4",
	"promotion": '',
  "url": 'url fo the product',
  "info": ''
}

```

#### Response

Status : 201

```
{
    "key": "gp:6cf81ddc-ee0d-4b8f-8fe4-0d6205d50f76:30ea88eb-5876-46d4-bd52-baabb45aaaa9",
    "total_prices": "1"
}

```
#### Request - Error
```
POST /geoprice/retailer_price/update?retailer_key=test&retailer_product_id=test1&retailer_store_id=walmarttest HTTP/1.1
Host: 127.0.0.1:5000
X-api-key: client_key
Content-Type: application/json

{
	"date": "20200420",
	"price": "20.50",
	"original_price": "30.99",
	"stock": "4",
	"promotion": '',
  "url": 'url fo the product',
  "info": ''
}

```

#### Response

Status : 400

```
{
    "errors": [
        {
            "code": "RP003",
            "description": null,
            "message": "No data found for the query"
        }
    ]
}


#### Request - All OK

``` 
GET /geoprice/retailer_price/get?retailer_key=walmart&retailer_product_id=test1&retailer_store_id=walmart1 HTTP/1.1
Host: 127.0.0.1:5000
X-api-key: client_key

```

#### Response 

Status 200

``` 
[
    {
        "date": "20200419",
        "original_price": "30.99",
        "price": "20.50",
        "promotion": '',
        "stock": "4",
        "url": "",
        "info": ""
    }
]
```
#### Request - Error

``` 
GET /geoprice/retailer_price/get?retailer_product_id=test1&retailer_store_id=walmart1 HTTP/1.1
Host: 127.0.0.1:5000
X-api-key: client_key

```

#### Response 

Status 400

``` 
{
    "errors": [
        {
            "code": "RP002",
            "description": "Must <retailer_key, retailer_product_id, retailer_store_id> OR <product_uuid, store_uuid>",
            "message": "Field is missing in request data"
        }
    ]
}
```
