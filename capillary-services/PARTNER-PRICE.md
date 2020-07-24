# Capillary Services Endpoints

## Website -Price and Stock -API

### Fields/Data Model


**uuid**

- Data type: uuid, Must
- Description: Product ID, could be product_uuid or byprice_uuid
- Validation: Should be a proper longitude
- Examples: f6bafc68-06b3-4c09-b044-978a0a7404f6 or 1d73aa2f-beee-426f-bbcd-f69556aaf873

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
- Examples: 10 or 30

**zip_code**

- Data type: int, optional but strongly recommended
- Description: Zip code to get prices from
- Validation: Should be an integer valid zip_code of 5 digits
- Examples: 06600 or 04920


#### Request

```
GET /capillary/website/item/get?uuid=6202a24c-c821-4f7a-bd96-f3b68bdef4c6&latitude=19.4326764&longitude=-99.1336339&radius=1 HTTP/1.1
Host: 35.193.29.21:8005

```

#### Response

Status : 200

```
{
    "geoprice": {
        "la_comer": [
            {
                "price": {},
                "store": {
                    "active_store_uuid": "60413a88-86cc-11e7-87b4-0242ac110002",
                    "distance": 0.4218,
                    "lat": 19.30520056795499,
                    "lng": -99.12769943475723,
                    "retailer_key": "la_comer",
                    "store_uuid": "60413a88-86cc-11e7-87b4-0242ac110002"
                }
            }
        ],
        "san_pablo": [
            {
                "price": {
                    "date": "20200716",
                    "original_price": "1898.00",
                    "price": "1898.00",
                    "promotion": "",
                    "stock": "0"
                },
                "store": {
                    "active_store_uuid": "e998775c-7b09-11e7-8760-80e6500152aa",
                    "address": "14310, Ciudad de México, TLALPAN, Mexico",
                    "city": "Tlalpan",
                    "contact_email": null,
                    "contact_phone": "(55) 5354 9000",
                    "country": "Mexico",
                    "created_at": "Thu, 25 Jun 2020 19:49:50 GMT",
                    "delivery_cost": 0,
                    "delivery_radius": 4,
                    "delivery_time": "40 a 90 minutos",
                    "distance": 0.869,
                    "is_active": false,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.3008,
                    "lng": -99.1246,
                    "locality": "México Belisario Domínguez",
                    "min_amount": 1,
                    "name": "(MIRAMONTES) FARMACIA SAN PABL",
                    "retailer_key": "san_pablo",
                    "retailer_store_id": "0018",
                    "scraper_store_id": null,
                    "source": "byprice",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "fb2414e2-7b09-11e7-8578-80e6500152aa",
                    "timing": "De 06:00 a 01:00",
                    "updated_at": "Thu, 25 Jun 2020 19:49:50 GMT",
                    "updated_by": "website",
                    "zip": "14310"
                }
            },
            {
                "price": {
                    "date": "20200716",
                    "original_price": "1898.00",
                    "price": "1898.00",
                    "promotion": "",
                    "stock": "0"
                },
                "store": {
                    "active_store_uuid": "e998775c-7b09-11e7-8760-80e6500152aa",
                    "address": "04890, Ciudad de México, COYOACAN, Mexico",
                    "city": "Coyoacán",
                    "contact_email": null,
                    "contact_phone": "(55) 5354 9000",
                    "country": "Mexico",
                    "created_at": "Thu, 25 Jun 2020 19:49:46 GMT",
                    "delivery_cost": 0,
                    "delivery_radius": 4,
                    "delivery_time": "40 a 90 minutos",
                    "distance": 0.8682,
                    "is_active": false,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.3163,
                    "lng": -99.1266,
                    "locality": "México Los Olivos",
                    "min_amount": 1,
                    "name": "(M-FOVISSSTE) FARMACIA SAN PAB",
                    "retailer_key": "san_pablo",
                    "retailer_store_id": "0073",
                    "scraper_store_id": null,
                    "source": "byprice",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "f939edd0-7b09-11e7-b7c1-80e6500152aa",
                    "timing": "De 06:00 a 01:00",
                    "updated_at": "Thu, 25 Jun 2020 19:49:46 GMT",
                    "updated_by": "website",
                    "zip": "04890"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "Valextra ",
        "byprice_presentation_id": null,
        "byprice_similar_id": null,
        "byprice_uuid": "aae52a24-f038-4c7a-8cb4-ae8b3eb71dcc",
        "category1": "Antiinfeccioso",
        "category2": "Antiinfeccioso",
        "category3": null,
        "category4": null,
        "category5": null,
        "created_at": "Tue, 28 Apr 2020 17:47:27 GMT",
        "historic_ids": null,
        "image": [
            "https://byprice-prod-images.s3-us-west-2.amazonaws.com/9f36f7bb-2aa7-45b4-882e-99f1b4f72f70/0.png",
            "https://byprice-prod-images.s3-us-west-2.amazonaws.com/9f36f7bb-2aa7-45b4-882e-99f1b4f72f70/1.png"
        ],
        "is_active": true,
        "is_centralized": false,
        "is_manually_verified": true,
        "is_online": true,
        "is_prescription": false,
        "is_visible": true,
        "laboratory": null,
        "long_description": null,
        "matching_score": 100,
        "name": "Valextra con 42 Tabletas (500 mg)",
        "price": 1897,
        "product_uuid": "1d73aa2f-beee-426f-bbcd-f69556aaf873",
        "retailer_key": "farmazone",
        "retailer_product_id": "7501299330265",
        "retailer_product_url": null,
        "score": 0,
        "scraper_product_id": null,
        "seller": "FarmaZone",
        "short_description": "Valextra con 42 Tabletas Valaciclovir (500 mg)",
        "source": "farmazone",
        "tags": [],
        "universal_product_id": "7501299330265",
        "universal_product_id_type": "ean",
        "updated_at": "Thu, 09 Jul 2020 22:35:30 GMT",
        "updated_by": "website",
        "video": []
    },
    "item_type": "retailer_product"
}

```


#### Request

```
GET /capillary/best_price/partner_salespoints/get?radius=10&zip_code=06600 HTTP/1.1
OR
GET /capillary/best_price/partner_salespoints/get?radius=10&longitude=-99.163553&latitude=19.42586 HTTP/1.1
X-api-key: byprice_own_key
Host: 35.193.29.21:8005

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

#### Possible errors

##### Invalid zip_code
#### Request

```
GET /capillary/best_price/partner_salespoints/get?radius=10&zip_code=0660 HTTP/1.1
X-api-key: byprice_own_key
Host: 35.193.29.21:8005

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
Host: 35.193.29.21:8005

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


#### Request

```
POST /capillary/best_price/partner_price/get?universal_product_id=7501409201041 HTTP/1.1
Host: 35.193.29.21:8005
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

#### Possible errors

##### Invalid uuid
#### Request

```
GET /capillary/best_price/partner_price/get?universal_product_id=75012993302650 HTTP/1.1
X-api-key: byprice_own_key
Host: 35.193.29.21:8005

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