### Get all retailer products

#### Request

##### HTTP
```
GET /catalog/retailer_product/get/all?page=1 HTTP/1.1
Host: api.saludmexico.org
X-api-key: byprice_generated_key

```

##### cURL
``` 
curl --location --request GET 'https://api.saludmexico.org/catalog/retailer_product/get/all?page=3' \
--header 'X-api-key: byprice_generated_key'

``` 

#### Parameters

| parameter         | mandatory | data type | default |
|-------------------|-----------|-----------|---------
| **page**          |    yes    |    int    | 1
| **retailer_key**  |    no     |    str    |


#### Response

Status 200

```
{
    "products": [
        {
            "attribute": {},
            "brand": "Almetec ",
            "category1": "Sistema Cardiovascular",
            "category2": "Cardiologia",
            "category3": null,
            "category4": null,
            "category5": null,
            "image": [
                "https://byprice-prod-images.s3-us-west-2.amazonaws.com/66cf1391-02ac-4f94-b4e3-805597566c4b/0.png"
            ],
            "is_active": true,
            "is_prescription": false,
            "is_visible": true,
            "laboratory": null,
            "long_description": null,
            "name": "Almetec con 14 Tabletas Olmesartán (20 mg)",
            "product_uuid": "5aeeecfd-e140-4249-9c15-5c7edea08f45",
            "retailer_product_id": "7501050617154",
            "short_description": "Almetec con 14 Tabletas Olmesartán (20 mg)",
            "universal_product_id": "7501050617154",
            "universal_product_id_type": "ean",
            "video": []
        },
        {
            "attribute": {},
            "brand": "Remeron Soltab",
            "category1": "Sistema Nervioso",
            "category2": "Psicoanalépticos",
            "category3": null,
            "category4": null,
            "category5": null,
            "image": [
                "https://byprice-prod-images.s3-us-west-2.amazonaws.com/ed6ee74a-1a2c-49cf-87fc-f99e6e93b3f9/0.png"
            ],
            "is_active": true,
            "is_prescription": false,
            "is_visible": true,
            "laboratory": null,
            "long_description": null,
            "name": "Remeron Soltab con 30 Tabletas (30 mg)",
            "product_uuid": "e90adf77-71b0-40bd-97f2-ac7c8c2a7038",
            "retailer_product_id": "7501409201607",
            "short_description": "Remeron Soltab con 30 Tabletas Mirtazapina (30 mg)",
            "universal_product_id": "7501409201607",
            "universal_product_id_type": "ean",
            "video": []
        },
    //.
    //.
    //.
    ],
    "total_pages": 65,
    "total_products": 32037
}

```