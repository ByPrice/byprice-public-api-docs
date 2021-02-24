## Retailer Product - API

### RetailerProduct Partner Model

**retailer_product_id**

- Data type: str, Must
- Description: unique identifier from retailer
- Validation: No specific validation
- Example: rappi244

**universal_product_id**

- Data type: str, Must
- Description: unique global identifier for product
- Validation: No specific validation
- Example: 07528836918364

**universal_product_id_type**

- Data type: str, Must
- Description: unique product identifier type
- Validation: No specific validation
- Example: gtin or upc or ean or ispn

**name**

- Data type: str, Must
- Description: product name
- Validation: No validation required
- Examples: "Chocolate oscuro Carlos V 180 gr"

**category1**

- Data type: str, Must
- Description: Parent category (Department)
- Validation: No specific validation
- Example: Farmacia o Despensa

**category2**

- Data type: str, Must
- Description: Child category from previous one
- Validation: No specific validation
- Example: Carnes or Enlatados

**category3**

- Data type: str, optional
- Description: Child category from previous one
- Validation: No specific validation
- Example: Carnes or Enlatados

**category4**

- Data type: str, optional
- Description: Child category from previous one
- Validation: No specific validation
- Example: Carnes or Enlatados

**category5**

- Data type: str, optional
- Description: Child category from previous one
- Validation: No specific validation
- Example: Carnes or Enlatados

**brand**

- Data type: str, Must
- Description: product brand
- Validation: No specific validation
- Example: nestlé or kelloggs

**tags**

- Data type: list, optional
- Description: seo, search tags for the product
- Validation: Should be a list
- Example: ['medicine', 'farmacy', 'flu']

**short_description**

- Data type: str, Must
- Description: short product descrption
- Validation: No specific validation
- Example: "Blanqueador Cloralex El Rendidor 950 ml"

**long_description**

- Data type: str, optional
- Description: complete description op product; usage benefits, usage instruvtions, etc
- Validation: No specific validation
- Example: "Cloralex El Rendidor en uso directo o diluido desinfecta totalmente agua, vegetales, trastes, piel, superficies cerámicas, superficies plásticas. Blanquea desodoriza y desinfecta telas blancas o de colores firmes de algodón, lino y poliéster, utensilios y áreas de mascotas, eliminando el 99.9% de hongos, virus y bacterias que provocan enfermedades como Influenza A(H1N1), Influenza A(H3N2), Influenza A(H7N9), Rhinovirus tipo 37, Rotavirus, RSV y Hepatitis A. Todas las presentaciones cuentan con Sellalum el sello de garantía que permite que el producto no sea adulterado."

**attribute**

- Data type: dict, optional
- Description: json with product attributes according to category
- Validation: json format
- Example:

```json
{
  "type": "tablet or capsule or gel or syrup or powder",
  "unit_weight": "200 g",
  "unit_volume": "ml",
  "unit_dimention": {
    "length": "cm",
    "breadth": "cm",
    "height": "cm"
  },
  "total_weight": "3",
  "total_volume": "5",
  "total_dimention": {
    "length": "1 cm",
    "breadth": "1 cm",
    "height": "5 cm"
  },
  "total_unit": "12",
  "ingrident": {
    "Ibuprofeno": "325 mg",
    "Paracetamol": "200 mg"
  },
  "color": "red or blue or green etc",
  "size": "small or medium or large etc"
}
```

**retailer_key**

- Data type: str, Must
- Description: Unique retailer keyword
- Validation: All lowercase, no spaces, will be generated manually by byprice
- Example: la_comer or walmart

**laboratory**

- Data type: str, optional
- Description: Laboratory which produces the product (midicin)
- Validation: No specific validation
- Example: bayer or msd

**seller**

- Data type: str, optional
- Description: Seller or provider of product
- Validation: No specific validation
- Example: xiaomi or la_comer

**price**

- Data type: decimal, Must. This is just the reference price. We do not use this on the website.
- Description: Price of the product, must be 2 decimal places
- Validation: 2 decimal places, Non-negative, should be greater than 0
- Examples: 50.00 or 100.99 or 75.50

**is_active**

- Data type: bool, Must.
- Description: If product is active. Put is_active = False if you to delete the product. Put True if you do not know.
- Validation: Should be bool
- Examples: True or False

**is_visible**

- Data type: bool, Must
- Description: Product might be active but not visible on the website, because of stock or payment or old data or any other business reason. Put True if you do not know.
- Validation: Should be bool
- Examples: True or False

**is_centralized**

- Data type: bool, Must
- Description: If the product has same price and stock over all its store. Put False if you do not know.
- Validation: Should be bool
- Examples: True or False

**is_online**

- Data type: bool, Must
- Description: If product is online. Put True if you do not know.
- Validation: Should be bool
- Examples: True or False

**retailer_product_url**

- Data type: str, optional
- Description: url of product
- Validation: Shold be a valid url
- Examples: https://super.walmart.com.mx/articulos-de-lavanderia/blanqueador-cloralex-el-rendidor-950-ml/00000007500061


**image**

- Data type: list, optional
- Description: list of url images
- Validation: Should be a list
- Example: ['https://www.chedraui.com.mx/medias/2503530-00-CH1200Wx1200H?context=bWFzdGVyfHJvb3R8NzU4NzF8aW1hZ2UvanBlZ3xoYzAvaGMwLzg4MDA3ODgzODE3MjYuanBnfGY5OWM1MjA2YjJjODg3MDhiOTBjMDM0ZTI3NWZjNjYxYTU0MjMwNDE0ZmM1YzA2M2E0MGExNjM1MDNjZjY2YmE']

**video**

- Data type: list, optional
- Description: list of url videos
- Validation: Should be a list


**special_requirement**
- Data type: dict, optional
- Description: json with product special requirements
- Validation: json format
- Example:

```json
{
  "high_cost": false,
  "refrigeration": false,
  "fraction": 4,
  "controlled_medicine": false
}
```


### Add product

#### Request - All ok

```
POST /catalog/retailer_product/add HTTP/1.1
Host: localhost:5000
X-api-key: KEY2
Content-Type: application/json

{   
    "retailer_product_id": "test11",
    "universal_product_id": "12345678901234",
    "universal_product_id_type": "gtin",
    "name": "This is a test prdoct created for test",
    "category1": "medicine",
    "category2": "testing",
    "category3": "not_compulsory",
    "category4": "not_compulsory",
    "category5": "not_compulsory",
    "brand": "testing_brand",
    "tags":["seo", "search", "important", "tags", "for", "the", "product", "max", "5", "only"],
    "short_description":"Short description of the product. 3-4 line description of the product is good. This might include some bullet points or specifications of the product.",
    "long_description":"Very long description of the product. Complete description of the product. Its use case , Side effaect. 9-10 lines would be enough.",
    "attribute": {
    	"attribute_key": "attribute_value",
    	"Ingriedient_as_key": "may be comma seperated salt",
    	"Color": "Color of the product",
    	"Each contain": "number of pieces"
    },
    "retailer_key": "retailer_key",
    "laboratory": "laboratory name",
    "seller": "seller name",
    "price": 85.50,
    "is_active": true,
    "is_visible": true,
    "is_centralized":false,
    "is_online":false,
    "retailer_product_url":"url",
    "image":["url1", "url2", "url3"],
    "video":["url1", "url2"],
    "special_requirement": {
    	"controlled_medicine": false
    }
}

```

#### Response
Status 201
```

{
    "message": "The product is added successfully",
    "product_uuid": "ea827c68-df46-4908-8c69-12ac2369f61f",
    "request_uuid": null,
    "retailer_key": "retailer_key",
    "retailer_product_id": "test12"
}

```

#### Request - Error

```
POST /catalog/retailer_product/add HTTP/1.1
Host: localhost:5000
X-api-key: KEY2
Content-Type: application/json

{   
    "retailer_product_id": "test11",
    "universal_product_id": "12345678901234",
    "universal_product_id_type": "gtin",
    "name": "This is a test prdoct created for test",
    "category1": "medicine",
    "category2": "testing",
    "category3": "not_compulsory",
    "category4": "not_compulsory",
    "category5": "not_compulsory",
    "brand": "testing_brand",
    "tags":["seo", "search", "important", "tags", "for", "the", "product", "max", "5", "only"],
    "short_description":"Short description of the product. 3-4 line description of the product is good. This might include some bullet points or specifications of the product.",
    "long_description":"Very long description of the product. Complete description of the product. Its use case , Side effaect. 9-10 lines would be enough.",
    "attribute": {
    	"attribute_key": "attribute_value",
    	"Ingriedient_as_key": "may be comma seperated salt",
    	"Color": "Color of the product",
    	"Each contain": "number of pieces"
    },
    "retailer_key": "retailer_key this is a f key",
    "laboratory": "laboratory name",
    "seller": "seller name",
    "price": 0,
    "is_active": true,
    "is_visible": true,
    "is_centralized":false,
    "is_online":false,
    "retailer_product_url":"Would be verified in next version",
    "image":["url1", "url2", "url3"],
    "video":["url1", "url2"]
}

```

#### Response

Status 400
```
{
    "errors": [
        {
            "code": "RP006",
            "description": "price should be grater then 1.00 and less then 1000000.00 ",
            "message": "Invalid price, too high or too low"
        }
    ]
}
```
### Update Retailer Product

#### Request - All ok
```

POST /catalog/retailer_product/update?retailer_product_id=test10&retailer_key=retailer_key HTTP/1.1
Host: localhost:5000
X-api-key: KEY2
Content-Type: application/json

{
    "tags":["SEO", "SEARCH", "important", "tags", "for", "the", "product", "max", "5", "only"],
    "long_description":"Very fake test long description of the product. Complete description of the product. Its use case , Side effaect. 9-10 lines would be enough.",
    "attribute": {
    	"attribute_key": "attribute_value",
    	"Ingriedient_as_key": "may be comma seperated salt",
    	"Color": "Color of the product",
    	"Each contain": "number of pieces"
    },
    "retailer_key": "retailer_key this is a f key",
    "seller": "seller name",
    "price": 90.00,
    "is_active": false,
    "is_visible": true,
    "is_online":true,
    "matching_score": null,
    "retailer_product_url":"https://byprice.com/papel-higienico-kleenex-cottonelle-cottonelle-soft-care-32-rollos-con-180-hojas-dobles-producto/0193e24d-6b30-40c5-931c-7ff7c4352e6e",
    "image":["url1", "url2", "url3", "url4"],
    "video":["url1", "url2", "url3"],
    "scraper_product_id":null,
    "special_requirement": {
    	"high_cost": true,
        "refrigeration": true,
        "fraction": 5
    }

}

```

#### Response

Status 201

```

{
    "fields_updated": [
        "tags",
        "long_description",
        "price",
        "is_active",
        "is_visible",
        "is_online",
        "retailer_product_url",
        "image",
        "video"
        "special_requirement"
    ],
    "message": "The product is  updated successfully",
    "product_uuid": "865737c2-fd93-46cb-b59a-848d81f32a08",
    "request_uuid": null,
    "retailer_key": "retailer_key",
    "retailer_product_id": "test10"
}

```
#### Request - Error
```

POST /catalog/retailer_product/update?retailer_product_id=test10&retailer_key=retailer_key this is a f key HTTP/1.1
Host: localhost:5000
X-api-key: KEY2
Content-Type: application/json

{
    "tags":["SEO", "SEARCH", "important", "tags", "for", "the", "product", "max", "5", "only","med"],
    "long_description":"Very fake test long description of the product. Complete description of the product. Its use case , Side effaect. 9-10 lines would be enough.",
    "attribute": {
    	"attribute_key": "attribute_value",
    	"Ingriedient_as_key": "may be comma seperated salt",
    	"Color": "Color of the product",
    	"Each contain": "number of pieces"
    },
    "retailer_key": "retailer_key this is a f key",
    "seller": "seller name",
    "price": 90.00,
    "is_active": false,
    "is_visible": true,
    "is_online":true,
    "matching_score": null,
    "retailer_product_url":"https://byprice.com/papel-higienico-kleenex-cottonelle-cottonelle-soft-care-32-rollos-con-180-hojas-dobles-producto/0193e24d-6b30-40c5-931c-7ff7c4352e6e",
    "image":["url1", "url2", "url3", "url4"],
    "video":["url1", "url2", "url3"],
    "scraper_product_id":null,
    "special_requirement": {
    	"high_cost": true,
        "refrigeration": true,
        "fraction": 5
    },
    "item_page_uuid":"cd318e2a-11d4-4fa7-811b-5890513e43b9",
    "is_purchasable":true,
    "boost_retailer_product_uuids":["7aa9a0a7-ac47-465e-8354-f789c7752697"]

}

```

#### Response

Status 400

``` 
{
    "errors": [
        {
            "code": "RP005",
            "description": null,
            "message": "Number of tags should not be more than 10"
        }
    ]
}
```

### Get retailer product

#### Request - All OK

```
GET /catalog/retailer_product/get?retailer_product_id=test10&retailer_key=retailer_key HTTP/1.1
Host: localhost:5000
X-api-key: KEY2

```

#### Response

Status 200

```
[
    {
        "attribute": {
            "Color": "Color of the product",
            "Each contain": "number of pieces",
            "Ingriedient_as_key": "may be comma seperated salt",
            "attribute_key": "attribute_value"
        },
        "brand": "testing_brand",
        "byprice_uuid": null,
        "category1": "medicine",
        "category2": "testing",
        "category3": "not_compulsory",
        "category4": "not_compulsory",
        "category5": "not_compulsory",
        "created_at": "Tue, 07 Apr 2020 19:39:01 GMT",
        "source": "byprice",
        "image": [
            "url1",
            "url2",
            "url3",
            "url4"
        ],
        "is_active": false,
        "is_centralized": false,
        "is_manually_verified": false,
        "is_online": true,
        "is_visible": true,
        "long_description": "Very fake test long description of the product. Complete description of the product. Its use case , Side effaect. 9-10 lines would be enough.",
        "matching_score": "0.00",
        "name": "This is a test prdoct created for test",
        "price": "90.00",
        "product_uuid": "865737c2-fd93-46cb-b59a-848d81f32a08",
        "retailer_key": "retailer_key this is a f key",
        "retailer_product_id": "test10",
        "retailer_product_url": "https://byprice.com/papel-higienico-kleenex-cottonelle-cottonelle-soft-care-32-rollos-con-180-hojas-dobles-producto/0193e24d-6b30-40c5-931c-7ff7c4352e6e",
        "score": 0,
        "scraper_product_id": null,
        "laboratory": "laboratory name",
        "seller": "seller name",
        "short_description": "Short description of the product. 3-4 line description of the product is good. This might include some bullet points or specifications of the product.",
        "special_requirement": {
            "high_cost": true,
            "refrigeration": true,
            "fraction": 4
        },
        "tags": [
            "SEO",
            "SEARCH",
            "important",
            "tags",
            "for",
            "the",
            "product",
            "max",
            "5",
            "only"
        ],
        "universal_product_id": "12345678901234",
        "universal_product_id_type": "gtin",
        "updated_at": "Tue, 14 Apr 2020 15:50:44 GMT",
        "updated_by": "website",
        "video": [
            "url1",
            "url2",
            "url3"
        ],
    "item_page_uuid":"cd318e2a-11d4-4fa7-811b-5890513e43b9",
    "is_purchasable":true,
    "boost_retailer_product_uuids":["7aa9a0a7-ac47-465e-8354-f789c7752697"]
    }
]

```

#### Request - Error

```
GET /catalog/retailer_product/get?retailer_product_id=test10&retailer_key=retailer_key HTTP/1.1
Host: localhost:5000
X-api-key: xyz

```

#### Response

Status 401

```
{
    "errors": [
        {
            "code": "IA003",
            "description": null,
            "message": "You are trying to access protected/internal resource"
        }
    ]
}
```

### Get all retailer products


#### Parameters

| parameter         | mandatory | data type |
|-------------------|-----------|-----------|
| **page**          |    yes    |    int    |
| **retailer_key**  |    yes     |    str    |

#### Request - All OK

```
GET /catalog/retailer_product/get/all?page=1 HTTP/1.1
Host: localhost:5000
X-api-key: KEY2

```
#### Response

Status 200

```
{
    "products": [
        {
            "brand": "Ensure",
            "category1": "Vitaminas y Suplementos",
            "created_at": "Sat, 16 May 2020 00:20:13 GMT",
            "name": "Suplemento Alimenticio Ensure Advance Vainilla Botella 237 mL",
            "price": 50.00,
            "product_uuid": "02f40e85-cefa-4254-ab3c-d04e09fb06ec",
            "retailer_key": "rappi_benavides",
            "retailer_product_id": "00000000000975457175",
            "short_description": "Suplemento Alimenticio Ensure Advance Vainilla Botella 237 mL",
            "source": "byprice",
            "universal_product_id": "7501033958717",
            //...
        },
        {
            "name": "Virlix 10 mg 20 Tabletas Recubiertas - 8271",
            "price": 468.00,
            "retailer_key": "gofarma",
            "retailer_product_id": "d2b0ab1b-e535-11e6-ab18-06e0cabe8fd1",
            "seller": "gofarma",
            "short_description": "Virlix 10 Mg. 20 Tabletas Recubiertas",
            "source": "byprice",
            //...
        },
        //...
    ],
    "total_pages": 65,
    "total_products": 32037
}

```
#### Request - Error

```
GET /catalog/retailer_product/get/all?page=1 HTTP/1.1
Host: localhost:5000
X-api-key: xyz

```
#### Response

Status 401

```
{
    "errors": [
        {
            "code": "IA003",
            "description": null,
            "message": "You are trying to access protected/internal resource"
        }
    ]
}
```

### Delete retailer key

#### Request - All OK

```
POST /catalog/retailer_product/delete?retailer_product_id=test10&retailer_key=retailer_key HTTP/1.1
Host: localhost:5000
X-api-key: KEY2


```

#### Response

Status 201

```
{
    "message": "Product deleted successfully",
    "product_uuid": "865737c2-fd93-46cb-b59a-848d81f32a08",
    "retailer_key": "retailer_key",
    "retailer_product_id": "test10"
}

```
#### Request - Error

```
POST /catalog/retailer_product/delete?retailer_product_id=test10&retailer_key=retailer_key HTTP/1.1
Host: localhost:5000
X-api-key: KEY2


```

#### Response

Status 400

```
{
    "errors": [
        {
            "code": "DB000",
            "message": "Class 'builtins.NoneType' is not mapped"
        }
    ]
}

```
