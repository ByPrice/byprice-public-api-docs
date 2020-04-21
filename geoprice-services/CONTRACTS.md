# Geoprice Services Endpoints

## Retailer Price and Stock -API

#### Fields/Data Model

**date** 

* Data type: int, Must
* Description: Date when the data is updated in the format YYYYMMDD  
* Validation: Should be a proper date
* Examples: 20200413 or 20191228
    
**price** 
* Data type: decimal, Must
* Description: Price of the product,  must be 2 decimal places 
* Validation: 2 decimal places, Non-negative, should be greater than 0
* Examples:  50.00 or 100.99 or 75.50
     
**original_price**
* Data type: decimal, Must
* Description: Original price of the product. Must be 2 decimal places, Faded price. If not available, should be same us price 
* Validation: 2 decimal places, Non-negative, should be greater than 0
* Examples:  60.00 or 140.99 or 85.50

**stock**
* Data type: int , Must
* Description: -1 out_of_stock, 0 means available, more than 0 means we have real_stock available
* Validation: 
* Examples: 0 or -1 or 1 or 10 or 100

**promotion**
* Data type: string, optional
* Description: Any kind of promotion for the product 
* Validation:
* Examples : 2X1 or 10% on all BBVA credit card


### Update Price

#### Request

```
POST /geoprice/retailer_price/update?retailer_key=walmart&retailer_product_id=test1&retailer_store_id=walmart1 HTTP/1.1
Host: 127.0.0.1:5000
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

#### Response

Status : 201

```
{
    "key": "a1b534bd-327e-47d6-9ff0-65c7b805f45a:a1b534bd-427e-47d6-9ff0-65c7b805f45a",
    "total_prices": 5
}

```
Response Fields

total_keys: How many times you have updated the price for that product


### Get Retailer Price

#### Request

``` 
GET /geoprice/retailer_price/get?retailer_key=walmart&retailer_product_id=test1&retailer_store_id=walmart1 HTTP/1.1
Host: 127.0.0.1:5000
X-api-key: client_key

```

#### Response 

Status: 200

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