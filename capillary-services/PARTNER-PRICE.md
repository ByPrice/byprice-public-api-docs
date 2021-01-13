# Capillary Services Endpoints

## Partner - Salespoints and Pricing -API

### Fields/Data Model

**uuid**

- Data type: uuid, Must
- Description: Product ID, could be product_uuid or byprice_uuid
- Validation: Should be a proper uuid
- Examples: f6bafc68-06b3-4c09-b044-978a0a7404f6 or 1d73aa2f-beee-426f-bbcd-f69556aaf873

**universal_product_id**

- Data type: ean or gtin, Must
- Description: Universal Product ID, could be ean or gtin
- Validation: Should be a proper ean or gtin
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
- Validation: Should be an integer from 1 to 10
- Examples: 3 or 10

**zip_code**

- Data type: int, optional
- Description: Zip code to get prices from
- Validation: Should be a valid zip_code of 5 digits
- Examples: 06600 or 04920

### Endpoints

### Get API for best dynamic prices according to universal product id

#### Parameters

| parameter                | group | mandatory | data type |
|--------------------------|-------|-----------|-----------|
| **universal_product_id** |  a    |    yes    |    str    |
| **latitude**             |  b    |    yes    |    float  |
| **longitude**            |  b    |    no     |    float  |
| **zip_code**             |  b    |    no     |    str    |

##### Note
- Parameters within the same group should be used together
- At least one optional parameter in group **b** must be present

#### Request

```
GET /capillary/tu_farmacia/best_price/get?universal_product_id=7501385410000&latitude=19.398975111965896&longitude=-99.15226846933365 HTTP/1.1
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
                    "address": "Icacos 38, Narvarte",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5559546279",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 0.0044,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.399,
                    "lng": -99.1523,
                    "locality": "Benito Juárez",
                    "min_amount": 1.0,
                    "name": "FarmaZone Narvarte",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "1",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:35 GMT",
                    "updated_by": "website",
                    "zip": "03100"
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
                    "address": "Arteaga 39, San angel",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5513137476",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:38 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 7.5482,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.3424,
                    "lng": -99.192,
                    "locality": "Álvaro Obregón",
                    "min_amount": 1.0,
                    "name": "FarmaZone San Angel",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "3",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:37 GMT",
                    "updated_by": "website",
                    "zip": "01000"
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
                    "address": "Lago Ilopango 19,Torre blanca",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5552662785",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 7.8019,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.4553,
                    "lng": -99.1966,
                    "locality": "Miguel Hidalgo",
                    "min_amount": 1.0,
                    "name": "FarmaZone Polanco",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "2",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:36 GMT",
                    "updated_by": "website",
                    "zip": "11280"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "CUERPO",
        "byprice_presentation_id": null,
        "byprice_similar_id": null,
        "byprice_uuid": null,
        "category1": "SISTEMA GENITOURINARIO",
        "category2": "TERAPIA HORMONAL",
        "category3": null,
        "category4": null,
        "category5": null,
        "created_at": "Tue, 28 Apr 2020 17:46:13 GMT",
        "historic_ids": null,
        "image": [
            "https://ws.go-smart.com.mx/farmazone/imagenes/7501385410000.jpg"
        ],
        "is_active": false,
        "is_centralized": false,
        "is_manually_verified": false,
        "is_online": true,
        "is_prescription": false,
        "is_visible": true,
        "laboratory": null,
        "long_description": null,
        "matching_score": 0.0,
        "name": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "price": 664.0,
        "product_uuid": "72adeb3c-af23-4010-bd2d-7c3e6e06e0a6",
        "retailer_key": "farmazone",
        "retailer_product_id": "7501385410000",
        "retailer_product_url": null,
        "score": 0,
        "scraper_product_id": null,
        "seller": "FarmaZone",
        "short_description": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "source": "farmazone",
        "special_requirement": {
            "controlled_medicine": false
        },
        "tags": [],
        "universal_product_id": "7501385410000",
        "universal_product_id_type": "ean",
        "updated_at": "Wed, 13 Jan 2021 16:20:33 GMT",
        "updated_by": "website",
        "video": []
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

### Get salespoints from this endpoint 

#### Request - All OK

```
GET /capillary/tu_farmacia/salespoints/get?zip_code=06600 HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
```

#### Response 

Status : 200

``` 
{
    "chedraui": [
        {
            "active_store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005",
            "distance": 2.1495,
            "lat": 19.428801175847838,
            "lng": -99.14329916238785,
            "retailer_key": "chedraui",
            "store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005"
        },
        {
            "active_store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005",
            "distance": 4.8787,
            "lat": 19.441844850933798,
            "lng": -99.2068675160408,
            "retailer_key": "chedraui",
            "store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005",
            "distance": 9.989,
            "lat": 19.48640017947266,
            "lng": -99.09320086240768,
            "retailer_key": "chedraui",
            "store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005"
        }
    ],
    "city_market": [
    ...                             ...
    ...                             ...
    ...                             ...
    "walmart": [
        {
            "active_store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003",
            "distance": 2.2335,
            "lat": 19.44329978087925,
            "lng": -99.1529980301857,
            "retailer_key": "walmart",
            "store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003"
        },
        {
            "active_store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5",
            "distance": 3.5612,
            "lat": 19.419399895067848,
            "lng": -99.13030117750168,
            "retailer_key": "walmart",
            "store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003",
            "distance": 9.9229,
            "lat": 19.3844004652997,
            "lng": -99.07980054616928,
            "retailer_key": "walmart",
            "store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003"
        }
    ]
}
``` 
#### Request - Error

```
GET /capillary/tu_farmacia/salespoints/get?zip_code=066 HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
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

### Get prices according to the universal_product_id using the salespoints provided

#### Request - All OK

```
POST /capillary/tu_farmacia/geoprice/get?universal_product_id=7501385410000 HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
Content-Type: application/json
{
    "chedraui": [
        {
            "active_store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005",
            "distance": 2.1495,
            "lat": 19.428801175847838,
            "lng": -99.14329916238785,
            "retailer_key": "chedraui",
            "store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005"
        },
        {
            "active_store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005",
            "distance": 4.8787,
            "lat": 19.441844850933798,
            "lng": -99.2068675160408,
            "retailer_key": "chedraui",
            "store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005",
            "distance": 9.989,
            "lat": 19.48640017947266,
            "lng": -99.09320086240768,
            "retailer_key": "chedraui",
            "store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005"
        }
    ],
    "city_market": [
    ...                             ...
    ...                             ...
    ...                             ...
    "walmart": [
        {
            "active_store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003",
            "distance": 2.2335,
            "lat": 19.44329978087925,
            "lng": -99.1529980301857,
            "retailer_key": "walmart",
            "store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003"
        },
        {
            "active_store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5",
            "distance": 3.5612,
            "lat": 19.419399895067848,
            "lng": -99.13030117750168,
            "retailer_key": "walmart",
            "store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003",
            "distance": 9.9229,
            "lat": 19.3844004652997,
            "lng": -99.07980054616928,
            "retailer_key": "walmart",
            "store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003"
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
                    "date": "20210101",
                    "original_price": "664.00",
                    "price": "664.00",
                    "promotion": "",
                    "stock": "2"
                },
                "store": {
                    "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "address": "Icacos 38, Narvarte",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5559546279",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 3.2122,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.399,
                    "lng": -99.1523,
                    "locality": "Benito Juárez",
                    "min_amount": 1.0,
                    "name": "FarmaZone Narvarte",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "1",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:35 GMT",
                    "updated_by": "website",
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
                    "address": "Lago Ilopango 19,Torre blanca",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5552662785",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 4.7682,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.4553,
                    "lng": -99.1966,
                    "locality": "Miguel Hidalgo",
                    "min_amount": 1.0,
                    "name": "FarmaZone Polanco",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "2",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:36 GMT",
                    "updated_by": "website",
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
                    "address": "Arteaga 39, San angel",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5513137476",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:38 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 9.7509,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.3424,
                    "lng": -99.192,
                    "locality": "Álvaro Obregón",
                    "min_amount": 1.0,
                    "name": "FarmaZone San Angel",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "3",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "6a8c4757-bb9f-492b-ae7a-e17fe8a42aff",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:37 GMT",
                    "updated_by": "website",
                    "zip": "01000"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "CUERPO",
        "byprice_presentation_id": null,
        "byprice_similar_id": null,
        "byprice_uuid": null,
        "category1": "SISTEMA GENITOURINARIO",
        "category2": "TERAPIA HORMONAL",
        "category3": null,
        "category4": null,
        "category5": null,
        "created_at": "Tue, 28 Apr 2020 17:46:13 GMT",
        "historic_ids": null,
        "image": [
            "https://ws.go-smart.com.mx/farmazone/imagenes/7501385410000.jpg"
        ],
        "is_active": false,
        "is_centralized": false,
        "is_manually_verified": false,
        "is_online": true,
        "is_prescription": false,
        "is_visible": true,
        "laboratory": null,
        "long_description": null,
        "matching_score": 0.0,
        "name": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "price": 664.0,
        "product_uuid": "72adeb3c-af23-4010-bd2d-7c3e6e06e0a6",
        "retailer_key": "farmazone",
        "retailer_product_id": "7501385410000",
        "retailer_product_url": null,
        "score": 0,
        "scraper_product_id": null,
        "seller": "FarmaZone",
        "short_description": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "source": "farmazone",
        "special_requirement": {
            "controlled_medicine": false
        },
        "tags": [],
        "universal_product_id": "7501385410000",
        "universal_product_id_type": "ean",
        "updated_at": "Wed, 13 Jan 2021 16:20:33 GMT",
        "updated_by": "website",
        "video": []
    },
    "purchasable": true
}
``` 

#### Request - Error

```
POST /capillary/tu_farmacia/geoprice/get HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
Content-Type: application/json
{
    "chedraui": [
        {
            "active_store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005",
            "distance": 2.1495,
            "lat": 19.428801175847838,
            "lng": -99.14329916238785,
            "retailer_key": "chedraui",
            "store_uuid": "e4d4ef70-7b09-11e7-855a-0242ac110005"
        },
        {
            "active_store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005",
            "distance": 4.8787,
            "lat": 19.441844850933798,
            "lng": -99.2068675160408,
            "retailer_key": "chedraui",
            "store_uuid": "dfbe4950-7b09-11e7-855a-0242ac110005"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005",
            "distance": 9.989,
            "lat": 19.48640017947266,
            "lng": -99.09320086240768,
            "retailer_key": "chedraui",
            "store_uuid": "f2b86a4a-7b09-11e7-855a-0242ac110005"
        }
    ],
    "city_market": [
    ...                             ...
    ...                             ...
    ...                             ...
    "walmart": [
        {
            "active_store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003",
            "distance": 2.2335,
            "lat": 19.44329978087925,
            "lng": -99.1529980301857,
            "retailer_key": "walmart",
            "store_uuid": "17128984-7ace-11e7-9b9f-0242ac110003"
        },
        {
            "active_store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5",
            "distance": 3.5612,
            "lat": 19.419399895067848,
            "lng": -99.13030117750168,
            "retailer_key": "walmart",
            "store_uuid": "fe8024d1-e1a7-4d7d-b192-d426189758d5"
        },
        ...                     ...
        ...                     ...
        {
            "active_store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003",
            "distance": 9.9229,
            "lat": 19.3844004652997,
            "lng": -99.07980054616928,
            "retailer_key": "walmart",
            "store_uuid": "13ff934a-7ace-11e7-9b9f-0242ac110003"
        }
    ]
}
```

#### Response 

Status : 404
```
{
    "geoprice": {},
    "item": {},
    "item_type": "retailer_product"
} 
```

### Get byprice price according to the universal_product_id using the salespoints provided

#### Request - All OK

```
POST /capillary/tu_farmacia/geoprice/byprice/get?universal_product_id=7501385410000 HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
Content-Type: application/json
{
    "farmazone": [
        {
            "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
            "distance": 3.2161,
            "lat": 19.398975111965896,
            "lng": -99.15226846933365,
            "retailer_key": "farmazone",
            "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2"
        },
        {
            "active_store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
            "distance": 4.7662,
            "lat": 19.45525099114554,
            "lng": -99.19662147760391,
            "retailer_key": "farmazone",
            "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c"
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
                    "date": "20210101",
                    "original_price": "664.00",
                    "price": "664.00",
                    "promotion": "",
                    "stock": "2"
                },
                "store": {
                    "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "address": "Icacos 38, Narvarte",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5559546279",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 3.2161,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.399,
                    "lng": -99.1523,
                    "locality": "Benito Juárez",
                    "min_amount": 1.0,
                    "name": "FarmaZone Narvarte",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "1",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:35 GMT",
                    "updated_by": "website",
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
                    "address": "Lago Ilopango 19,Torre blanca",
                    "city": "Ciudad de Mexico",
                    "contact_email": "test@byprice.com",
                    "contact_phone": "5552662785",
                    "country": "Mexico",
                    "created_at": "Tue, 28 Apr 2020 18:47:37 GMT",
                    "delivery_cost": null,
                    "delivery_radius": 10.0,
                    "delivery_time": null,
                    "distance": 4.7662,
                    "is_active": true,
                    "is_online": true,
                    "is_visible": true,
                    "lat": 19.4553,
                    "lng": -99.1966,
                    "locality": "Miguel Hidalgo",
                    "min_amount": 1.0,
                    "name": "FarmaZone Polanco",
                    "retailer_key": "farmazone",
                    "retailer_store_id": "2",
                    "scraper_store_id": null,
                    "source": "farmazone",
                    "state": "Ciudad de Mexico",
                    "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
                    "timing": "Lunes a domingo 24 hrs.",
                    "updated_at": "Wed, 25 Nov 2020 20:10:36 GMT",
                    "updated_by": "website",
                    "zip": "11280"
                }
            }
        ]
    },
    "item": {
        "attribute": {},
        "brand": "CUERPO",
        "byprice_presentation_id": null,
        "byprice_similar_id": null,
        "byprice_uuid": null,
        "category1": "SISTEMA GENITOURINARIO",
        "category2": "TERAPIA HORMONAL",
        "category3": null,
        "category4": null,
        "category5": null,
        "created_at": "Tue, 28 Apr 2020 17:46:13 GMT",
        "historic_ids": null,
        "image": [
            "https://ws.go-smart.com.mx/farmazone/imagenes/7501385410000.jpg"
        ],
        "is_active": false,
        "is_centralized": false,
        "is_manually_verified": false,
        "is_online": true,
        "is_prescription": false,
        "is_visible": true,
        "laboratory": null,
        "long_description": null,
        "matching_score": 0.0,
        "name": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "price": 664.0,
        "product_uuid": "72adeb3c-af23-4010-bd2d-7c3e6e06e0a6",
        "retailer_key": "farmazone",
        "retailer_product_id": "7501385410000",
        "retailer_product_url": null,
        "score": 0,
        "scraper_product_id": null,
        "seller": "FarmaZone",
        "short_description": "Cuerpo Amarillo Fuerte IM Solucion Inyectable 2 mL Progesterona (50 mg)",
        "source": "farmazone",
        "special_requirement": {
            "controlled_medicine": false
        },
        "tags": [],
        "universal_product_id": "7501385410000",
        "universal_product_id_type": "ean",
        "updated_at": "Wed, 13 Jan 2021 16:20:33 GMT",
        "updated_by": "website",
        "video": []
    },
    "purchasable": true
}
``` 
#### Request - Error

```
POST /capillary/tu_farmacia/geoprice/byprice/get HTTP/1.1
Host: dev-api.byprice.com
x-api-key: byprice_own_key
Content-Type: application/json
{
    "farmazone": [
        {
            "active_store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2",
            "distance": 3.2161,
            "lat": 19.398975111965896,
            "lng": -99.15226846933365,
            "retailer_key": "farmazone",
            "store_uuid": "796cf89f-9214-4ee1-9dc9-a7063ede7ac2"
        },
        {
            "active_store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c",
            "distance": 4.7662,
            "lat": 19.45525099114554,
            "lng": -99.19662147760391,
            "retailer_key": "farmazone",
            "store_uuid": "a1df4159-c134-47a9-a2dc-9b3c361c6d3c"
        }
    ]
}
```

#### Response 

Status : 404
```
{
    "geoprice": {},
    "item": {},
    "item_type": "retailer_product"
} 
```