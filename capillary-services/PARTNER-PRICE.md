# Capillary Services Endpoints

## Website-Price and Stock -API

### Fields/Data Model


**universal_product_id**

- Data type: ean or gtin, Must
- Description: Universal Product ID, could be ean or gtin
- Validation: Should be a proper ean or gtin or bar code
- Examples: 7501409201041 or 7501299330265

**latitude**

- Data type: float, Must
- Description: Latitude of center point
- Validation: Should be a proper latitude
- Examples: 19.308533 or 19.336679

**longitude**

- Data type: float, Must
- Description: Longitude of center point
- Validation: Should be a proper longitude
- Examples: -99.125781 or -99.112842

**zip_code**

- Data type: int, optional but strongly recommended
- Description: Zip code to get prices from
- Validation: Should be an integer valid zip_code of 5 digits
- Examples: 06600 or 04920


### Get API for best dynamic prices according to universal product id

#### Parameters

| parameter                | group | mandatory | data type |
|--------------------------|-------|-----------|-----------|
| **universal_product_id** |  a    |    yes    |    str    |
| **latitude**             |  b    |    yes    |    float  |
| **longitude**            |  b    |    yes     |    float  |
| **zip_code**             |  b    |    yes     |    str    |

##### Note
- Parameters within the same group should be used together
- Either zip_code or latitude, longitude is must


#### Request

```
GET /capillary/tu_farmacia/best_price/get?universal_product_id=7501385410000&zip_code=06600 HTTP/1.1
Host: dev-api.byprice.com
X-api-key: byprice_own_key
Content-Type: application/json

```

#### Response

Status : 200

```
{
    "geoprice": {
        "byprice": [
            {
                "price": {
                    "date": "20210101",
                    "original_price": "664.00",
                    "price": "664.00",
                    "promotion": "",
                    "stock": "2"
                },
                "store": {
                    "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "distance": 3.2122,
                    "locality": "Benito Juárez",
                    "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "zip": "03100"
                }
            },
            {
                "price": {
                    "date": "20210101",
                    "original_price": "664.00",
                    "price": "664.00",
                    "promotion": "",
                    "stock": "2"
                },
                "store": {
                    "active_store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
                    "distance": 4.7682,
                    "locality": "Miguel Hidalgo",
                    "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
                    "zip": "11280"
                }
            },
            {
                "price": {
                    "date": "20210101",
                    "original_price": "664.00",
                    "price": "664.00",
                    "promotion": "",
                    "stock": "-1"
                },
                "store": {
                    "active_store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
                    "distance": 9.7509,
                    "locality": "Álvaro Obregón",
                    "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
                    "zip": "01000"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "CUERPO",
        "category1": "SISTEMA GENITOURINARIO",
        "category2": "TERAPIA HORMONAL",
        "category3": null,
        "image": [
            "https://ws.go-smart.com.mx/farmazone/imagenes/7501385410000.jpg"
        ],
        "is_prescription": false,
        "name": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "product_uuid": "72adeb3c-af23-4010-bd2d-7c3e6e06e0a6",
        "short_description": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "universal_product_id": "7501385410000"
    },
    "purchasable": true
}
```

#### Request - Error

```
GET /capillary/tu_farmacia/best_price/get?universal_product_id=7501385410000 HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
```

#### Response 

Status : 400

``` 
{
    "errors": [
        {
            "code": "IR001",
            "message": "Required arguments missing, zip_code or [latitude and longitude]"
        }
    ]
}
``` 
