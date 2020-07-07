## Store-API

### Fields/Data Model

**name**

- Data type: str, Must
- Description: Store name
- Validation: No validation required
- Examples: "Walmart Buenavista" or "La comer Polanco"

**retailer_key**

- Data type: str, Must
- Description: Retailer keyword to whom the store belongs
- Validation: All lowercase, no spaces, use \_ for spaces, will be generated manually by byprice.
- Examples: walmart or la_comer

**address**

- Data type: str, Must
- Description: Address of the store
- Validation: No validation required
- Examples: Av. Paseo de la Reforma 222

**country**

- Data type: str, Must
- Description: Country where the store is
- Validation: No validation required
- Examples: México or Colombia

**state**

- Data type: str, Must
- Description: State where the store is
- Validation: No validation required
- Examples: CDMX or Jalisco

**city**

- Data type: str, Must
- Description: City where the store is
- Validation: No validation required
- Examples: Cd. Juárez or Guadalajara

**locality**

- Data type: str, Must
- Description: Locality where the store is
- Validation: No validation required
- Examples: Juárez or Xochimilco

**zip**

- Data type: int, Must
- Description: Valid zip code of the store
- Validation: 5 digit number
- Examples: 06600 or 03100

**contact_phone**

- Data type: str, optional
- Description: Store contact phone
- Validation: No special validation
- Examples: 5500346627

**contact_email**

- Data type: str, optional
- Description: Store contact email
- Validation: No special validation
- Examples: conatcto_buenavista@walmart.com

**delivery_cost**

- Data type: float, optional
- Description: Price of the delivery service
- Validation: Should be a positive point number
- Examples: 0 or 50.0

**delivery_time**

- Data type: int, optional
- Description: Delivery time took for delivery in hours
- Validation: Should be a positive number
- Examples: 1

**timing**

- Data type: str, optional
- Description: Store opening time
- Validation: No special validation
- Examples: lun - vie 8:00 a 20:00, sab 10:00 a 14:00

### Add Store

#### Request

```
POST /catalog/store/add HTTP/1.1
Host: localhost:5000
X-api-key: KEY2
Content-Type: application/json

{
"name" : "Walmart Buenavista",
"retailer_key" : "walmart",
"source" : "byprice_scraper",
"address" : "Av. Insurgentes Nte. 131",
"retailer_store_id" : "walmart1",
"is_active" : false,
"is_visible" : true,
"is_online" : true,
"zip" : "06300",
"lat" : 19.4434757,
"lng" : -99.2233684,
"contact_phone" : "528007106352",
"contact_email" : "store@store.com",
"min_amount" : 2.00,
"delivery_radius" : 5,
"delivery_cost" : null,
"delivery_time" : "if delivery , less than a day",
"timing" : "Monday TO Friday 9:00 AM to 6PM",
"scraper_store_id" : "willbe_foreignkey_later"
}


```

#### Example 1 successful response

##### Response

Status 201

```
{
    "message": "The store is added successfully",
    "request_uuid": null,
    "retailer_key": "walmart",
    "retailer_store_id": "walmart1",
    "source": "byprice_scraper",
    "store_uuid": "88ac43b8-4a9b-4345-a7e0-a139836da4a9"
}

```

#### Example 2 successful response

##### Response

Status 201

```
{
    "message": "The store is added successfully",
    "request_uuid": null,
    "retailer_key": "sanborns",
    "retailer_store_id": "sanborns1",
    "source": "byprice_scraper",
    "store_uuid": "782343b8-4a9b-4345-a7e0-a139836da4a9"
}

```

#### Example 1 error response

Status 400

```
{
    "error": "ERROR:  duplicate key value violates unique constraint \"retailer_key_retailer_store_id_unique\"\nDETAIL:  Key (retailer_key, retailer_store_id)=(walmart, walmart1) already exists.\n"
}

```

#### Example 2 error response

Status 400

```

{
    "error": "ERROR:  null value in column \"name\" violates not-null constraint\nDETAIL:  Failing row contains (a859be2a-3a99-4794-9817-d21c67b04630, null, walmart, byprice, \"Av. Insurgentes Nte. 132\", walmart1, f, t, t, Mexico, Ciudad de México, Cuauhtémoc, Guerrero, 06300, 19.4434757, -99.2233684, 528007106352, store@store.com, 2.00, 5, null, if delivery , less than a day, \"Monday TO Friday 9:00 AM to 6PM\", willbe_foreignkey_later, 2020-07-03 18:28:55.602587, 2020-07-03 18:28:55.602639, website).\n"
}

```

### Get Store

#### Request

You can pass is_active filter with any kind of get request

```

GET /catalog/store/get?retailer_store_id=walmart1&retailer_key=walmart HTTP/1.1
or
GET /catalog/store/get?source=byprice_scraper&is_active=true HTTP/1.1
or
GET /catalog/store/get?store_uuid=88ac43b8-4a9b-4345-a7e0-a139836da4a9&is_active=true HTTP/1.1
Host: localhost:5000
X-api-key: KEY2

```

#### Example 1 successful Response

Status 200

```
[
    {
        "address": "Av. Insurgentes Nte. 131",
        "city": "Cuauhtémoc",
        "contact_email": "store2@store.com",
        "contact_phone": "008007106352",
        "country": "Mexico",
        "created_at": "Wed, 08 Apr 2020 23:22:19 GMT",
        "delivery_cost": "None",
        "delivery_radius": 50.0,
        "delivery_time": "if delivery , less2 than a day",
        "is_active": true,
        "is_online": true,
        "is_visible": true,
        "lat": 20.443455,
        "lng": 99.2233684,
        "locality": "México Guerrero",
        "min_amount": "2.00",
        "name": "Walmart Buenavista",
        "retailer_key": "walmart",
        "retailer_store_id": "walmart1",
        "scraper_store_id": "willbe_foreignkey_later",
        "source": "byprice_scraper",
        "state": "Ciudad de Mexico",
        "store_uuid": "88ac43b8-4a9b-4345-a7e0-a139836da4a9",
        "timing": "Monday TO Friday 9:00 AM t2o 6PM",
        "updated_at": "Wed, 08 Apr 2020 23:28:28 GMT",
        "updated_by": "website",
        "zip": "06300"
    }
]
```

#### Example 2 successful Response

Status 200

```
[
    {
        "address": "AV. COPILCO NO. 164 COL. OXTOPULCO DEL. COYOACAN",
        "city": "Coyoacán",
        "contact_email": null,
        "contact_phone": "['(0155) 5659 2790 ', ' 56 59 30 40']",
        "country": "Mexico",
        "created_at": "Thu, 25 Jun 2020 19:46:24 GMT",
        "delivery_cost": 39.00,
        "delivery_radius": 5.0,
        "delivery_time": "4 hrs",
        "is_active": true,
        "is_online": true,
        "is_visible": true,
        "lat": 19.3379,
        "lng": -99.1836,
        "locality": "México Barrio Oxtopulco Universidad",
        "min_amount": 1.00,
        "name": "COPILCO",
        "retailer_key": "walmart",
        "retailer_store_id": "0000002430",
        "scraper_store_id": null,
        "source": "byprice",
        "state": "Ciudad de Mexico",
        "store_uuid": "1471ddd8-7ace-11e7-9b9f-0242ac110003",
        "timing": "Lunes a Domingo 7:00 a 23:00",
        "updated_at": "Thu, 25 Jun 2020 19:46:24 GMT",
        "updated_by": "website",
        "zip": "04318"
    }
]
```

#### Example 1 error response

Status 400

```
{
    "error": "no_valid_fields_to_update"
}

```

#### Example 2 error response

Status 400

```
{
    "error": "invalid input syntax for type uuid: \"s3232\"\nLINE 3: WHERE catalog.store.store_uuid = 's3232'\n                                         ^\n"
}

```
