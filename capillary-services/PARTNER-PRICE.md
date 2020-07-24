# Capillary Services Endpoints

## Website -Price and Stock -API

### Fields/Data Model


**universal_product_id**

- Data type: ean or gtin, Must
- Description: Universal Product ID, could be ean or gtin
- Validation: Should be a proper longitude
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

**radius**

- Data type: int, optional but strongly recommended
- Description: Radius of area to get prices from
- Validation: Should be an integer from 1 to 100
- Examples: 3 or 10

**zip_code**

- Data type: int, optional but strongly recommended
- Description: Zip code to get prices from
- Validation: Should be an integer valid zip_code of 5 digits
- Examples: 06600 or 04920


#### Request

```
GET /capillary/best_price/partner_salespoints/get?radius=10&zip_code=06600 HTTP/1.1
OR
GET /capillary/best_price/partner_salespoints/get?radius=10&longitude=-99.163553&latitude=19.42586 HTTP/1.1
X-api-key: byprice_own_key
Host: api.saludmexico.org

```

#### Response

Status : 200

```
{
    "partner_salespoints": [
        {
            "active_store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
            "distance": 9.7546,
            "lat": 19.342374788477862,
            "lng": -99.19202953577042,
            "retailer_key": "byprice",
            "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff"
        },
        {
            "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
            "distance": 3.2161,
            "lat": 19.398975111965896,
            "lng": -99.15226846933365,
            "retailer_key": "byprice",
            "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2"
        },
        {
            "active_store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
            "distance": 4.7662,
            "lat": 19.45525099114554,
            "lng": -99.19662147760391,
            "retailer_key": "byprice",
            "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c"
        }
    ]
}

```

#### Request

```
POST /capillary/best_price/partner_price/get?universal_product_id=7501409201041 HTTP/1.1
Host: api.saludmexico.org
X-api-key: byprice_own_key
Content-Type: application/json

{
    "partner_salespoints": [
        {
            "active_store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
            "distance": 11.7651,
            "lat": 19.342374788477862,
            "lng": -99.19202953577042,
            "retailer_key": "byprice",
            "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff"
        },
        {
            "active_store_uuid": "750d6f46-f8a7-4542-a414-5636b346d0b2",
            "distance": 15.8853,
            "lat": 19.38819240815407,
            "lng": -99.27752763032913,
            "retailer_key": "byprice",
            "store_uuid": "750d6f46-f8a7-4542-a414-5636b346d0b2"
        }
    ]
}

```

#### Response

Status : 200

```
{
    "geoprice": {
        "byprice": [
            {
                "price": {
                    "date": "20200611",
                    "original_price": "2210.00",
                    "price": "1869.00",
                    "promotion": "",
                    "stock": "3"
                },
                "store": {
                    "active_store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
                    "distance": 11.7651,
                    "lat": 19.342374788477862,
                    "lng": -99.19202953577042,
                    "retailer_key": "byprice",
                    "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff"
                }
            },
            {
                "price": {
                    "date": "20200611",
                    "original_price": "2210.00",
                    "price": "1869.00",
                    "promotion": "",
                    "stock": "1"
                },
                "store": {
                    "active_store_uuid": "750d6f46-f8a7-4542-a414-5636b346d0b2",
                    "distance": 15.8853,
                    "lat": 19.38819240815407,
                    "lng": -99.27752763032913,
                    "retailer_key": "byprice",
                    "store_uuid": "750d6f46-f8a7-4542-a414-5636b346d0b2"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "Valextra ",
        "category1": "Antiinfeccioso",
        "category2": "Antiinfeccioso",
        "category3": null,
        "category4": null,
        "category5": null,
        "image": [
            "https://byprice-prod-images.s3-us-west-2.amazonaws.com/9f36f7bb-2aa7-45b4-882e-99f1b4f72f70/0.png",
            "https://byprice-prod-images.s3-us-west-2.amazonaws.com/9f36f7bb-2aa7-45b4-882e-99f1b4f72f70/1.png"
        ],
        "is_active": true,
        "is_prescription": false,
        "is_visible": true,
        "laboratory": null,
        "long_description": null,
        "name": "Valextra con 42 Tabletas (500 mg)",
        "product_uuid": "1d73aa2f-beee-426f-bbcd-f69556aaf873",
        "retailer_product_id": "7501299330265",
        "short_description": "Valextra con 42 Tabletas Valaciclovir (500 mg)",
        "universal_product_id": "7501299330265",
        "universal_product_id_type": "ean",
        "video": []
    },
    "item_type": "retailer_product"
}
```

### Possible errors

##### Invalid zip_code
#### Request

```
GET /capillary/best_price/partner_salespoints/get?radius=10&zip_code=0660 HTTP/1.1
X-api-key: byprice_own_key
Host: api.saludmexico.org

```

#### Response

Status : 400

```
{
    "errors": [
        {
            "code": "NF001",
            "message": "Data not found in database, zip_code"
        }
    ]
}

```

##### radius bigger than allowed radius
#### Request

```
GET /capillary/best_price/partner_salespoints/get?zip_code=06600&radius=15 HTTP/1.1
X-api-key: byprice_own_key
Host: api.saludmexico.org

```

#### Response

Status : 400

```
{
    "errors": [
        {
            "code": "IR004",
            "message": "Some condition is not satisfied for the request to continue, radius"
        }
    ]
}

```

##### Invalid universal_product_id
#### Request

```
GET /capillary/best_price/partner_price/get?universal_product_id=75012993302650 HTTP/1.1
X-api-key: byprice_own_key
Host: api.saludmexico.org

```

#### Response

Status : 200

```
{
    "geoprice": {},
    "item": {},
    "item_type": "retailer_product"
}

```