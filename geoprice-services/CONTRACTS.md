# Geoprice Services Endpoints

## Model 

Database:  Redis 
```
Key : product_uuid:store_uuid
Value : List , append at the end , only append if any of the field changes 
```

['date', 'price', 'original_price', 'stock', 'promotion']

* date (int) 20200413 , format - YYYYMMDD , must
* price Decimal 34.55 , must be 2 decimal places , must 
* original_price Decimal 40.00 , must be 2 decimal places , must , pass same as price if not possible
* stock int , # -1 out_of_stock, 0 means available, more than 0 means we have real_stock option , must
* promotion string , optional

## Retailer Price and Stock -API

### Update Price - For third party

#### Request

```
POST /geoprice/retailer_price/update?retailer_key=farmazone&retailer_product_id=test1&retailer_store_id= HTTP/1.1
Host: https://api.saludmexico.org
X-api-key: client_key
Content-Type: application/json

{
	"date":20200419,
	"price":20.50,
	"original_price": 30.99,
	"stock":4,
	"promotion":null
}

```

### Get Retailer Price

#### Request

``` 
GET /geoprice/retailer_price/get?retailer_key=farmazone&retailer_product_id=8027950210473&retailer_store_id=1 HTTP/1.1
Host: https://api.saludmexico.org
X-api-key: client_key

```

#### Response 

Status 200

``` 
[

    {
        "date": 20200413,
        "original_price": 30.99,
        "price": 25.99,
        "promotion": null,
        "stock": 6
    }
]


```
