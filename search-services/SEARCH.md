# Search Service Endpoints

## Search -Search -API

#### Request

```
GET /search/search?q=aspirin&sold_by_partner=true&latitude=25.706&longitude=-100.231&radius=10 HTTP/1.1
Host: localhost:8007
X-api-key: api_key
```

#### Parameters

| parameter           | description          | mandatory | data type |
| ------------------- | -------------------- | --------- | --------- |
| **q**               | universal product id | must      | string    |
| **sold_by_partner** | filter               | optional  | string    |
| **latitude**        | distance_filter      | optional  | float     |
| **longitude**       | distance_filter      | optional  | float     |
| **radius**          | distance_filter (km) | optional  | int       |

#### Notes

- If `q` parameter is empty, filters will not work, nothing will work
- `sold_by_partner` if true, the filter the results by sort_by_partner, in all other cases filter is not effective
- To filter by distance successfully, the three `distance_filter` parameters must be present

#### Response

Status : 200

```
{
    "filters": {},
    "items": [
        {
            "_score": 95.229485,
            "_yscore": 0.7964812867286246,
            "byprice_uuid": "c619b4dd-4748-4416-9411-a9faec8815b5",
            "image": [
                "https://byprice-prod-images.s3-us-west-2.amazonaws.com/2befb463-db6c-4179-9ef5-94aea3572439/0.png"
            ],
            "is_active": true,
            "is_prescription": false,
            "laboratories": [
                "Bayer"
            ],
            "name": "Aspirina con 100 Tabletas (500 mg)",
            "names": [
                "Aspirina Analgésico 100 Tabletas",
                "Aspirina 500 mg 100 Tabletas - 6152",
                "aspirina t 100 500 mg",
                "aspirina t 100 500 mg",
                "Aspirina 100 Tabletas (500 mg)",
                "aspirina 500 mg caja con 100 tabletas",
                "Aspirina 100 Tabletas Ãcido AcetilsalicÃ­lico (500 mg)",
                "Aspirina 500mg 100 Tabletas",
                "Aspirina 500Mg Tab 100",
                "  Aspirina 500 mg 100 tabletas",
                "aspirina t 100 500 mg",
                "aspirina adulto 100 tab"
            ],
            "product_uuid": null,
            "product_uuids": [
                "2befb463-db6c-4179-9ef5-94aea3572439",
                "968a65bd-2e4e-4409-b7fc-39fe2a6212b0",
                "ace9913e-feac-418e-909c-49629e5563a9",
                "bdb98c79-b5c1-4915-b67d-30a3fc382ed1",
                "df99eefb-6cbc-4904-bb89-eaa519b5755f",
                "a6c8f5d1-b497-40f9-9fdd-ec6cf983aebd",
                "14acf450-364d-42b1-98a0-219e42487278",
                "9b5cedbd-d365-4aea-8db9-baf050bc959b",
                "416b1f0e-8086-4899-99b8-419708f2273d",
                "52297011-a33e-44b7-84f6-7661987055d0",
                "94915d28-a28a-4093-a98b-ba787dcd30df",
                "0a418411-57d2-436d-8da6-63c956498989"
            ],
            "retailers": [
                "f_ahorro",
                "gofarma",
                "fresko",
                "la_comer",
                "rappi_benavides",
                "farmalisto",
                "farmazone",
                "farmaciasguadalajara",
                "chedraui",
                "walmart",
                "city_market",
                "soriana"
            ],
            "short_description": "Aspirina con 100 Tabletas Ácido Acetilsalicílico (500 mg)",
            "sold_by_partner": true,
            "tags": [
                "Aspirina",
                "Ácido Acetilsalicílico",
                "Alivio sintomático de los dolores leves o moderados"
            ],
            "universal_product_id": "7501008496152"
        },
        {
            "_score": 89.17959,
            "_yscore": 0.7458811164749152,
            "byprice_uuid": "cb5cefd4-b741-4dc8-aaec-03fb021e571b",
            "image": [
                "https://byprice-prod-images.s3-us-west-2.amazonaws.com/41472704-7a3c-4f50-a053-0ab696ec4374/0.png"
            ],
            "is_active": true,
            "is_prescription": false,
            "laboratories": [
                "Bayer"
            ],
            "name": "Aspirina Junior con 60 Tabletas (100 mg)",
            "names": [
                "ASPIRINA JR 100MG TAB CAJ C/60",
                "aspirina t 60 100 mg jr",
                "aspirina t 60 100 mg jr",
                "aspirina t 60 100 mg jr",
                "aspirina junior 60 tab",
                "Aspirina Junior 60 Tabletas (100 mg)",
                "Aspirina Junior Analgésico 60 tabletas",
                "aspirina infantil 60 tab",
                "Aspirina Junior 60 Tabletas",
                "Aspirina Tabletas Junior, 100 mg",
                "Aspirina junior  60 tabletas",
                "aspirina junior 100 mg caja con 60 tabletas",
                "Aspirina Infantil C60 Tab",
                "Aspirina Junior 60 Tabletas",
                "Aspirina 100 Mg Oral Inf 60  Tabletas",
                "  Aspirina junior 100 mg 60 tabletas",
                "Aspirina Junior 100 mg 60 Tabletas - 4226",
                "Aspirina Para niño",
                "Aspirina Junior 60 Tabletas Acido Acetilsalicilico (100 mg)"
            ],
            "product_uuid": null,
            "product_uuids": [
                "f121f24a-864d-11e9-8827-548ca04867a6",
                "58e4b089-1771-46b1-b47b-85cec3e2c461",
                "4f90a1ba-d575-4e2b-b0a8-12d956a18b1c",
                "e94a2122-ac4e-4cf6-86fc-4216162e0678",
                "41472704-7a3c-4f50-a053-0ab696ec4374",
                "2d9b6803-014d-4f6d-a9c7-a80b0e81d6e8",
                "a795096b-e016-4521-b431-ec382f0a7880",
                "3b967938-2793-4fbf-a74f-c80771196e62",
                "ec7398c7-7b71-4d16-aa94-578d756aea6b",
                "42a4f5a0-ca83-44bd-9c0c-2b0a2b2b53a8",
                "1f1b9efc-4fed-4542-a99b-11d70c3c9353",
                "88c5916b-171f-4cd9-83a7-abfa958f3c9d",
                "afc44fa0-90ad-43b4-847c-96ddaed71972",
                "85ef4c05-041f-4576-a317-20a715b94cb4",
                "78cdcf1d-f363-44f8-a123-5c54fb5fb64a",
                "345c137a-251d-4035-bb43-1d28f0f0966a",
                "44542be0-370f-471c-a974-cf14ceb97751",
                "c6a67782-23a5-4686-bb5c-9f1f9842adf6",
                "8abe71c9-afbe-4d8f-bf90-eb9b07a18b70"
            ],
            "retailers": [
                "farmacias_especializadas",
                "la_comer",
                "city_market",
                "fresko",
                "superama",
                "rappi_benavides",
                "f_ahorro",
                "soriana",
                "farmaciasguadalajara",
                "amazon",
                "cornershop",
                "farmalisto",
                "chedraui",
                "sanborns",
                "f_ahorro",
                "walmart",
                "gofarma",
                "san_pablo",
                "farmazone"
            ],
            "short_description": "Aspirina Junior con 60 Tabletas Ácido Acetilsalicílico (100 mg)",
            "sold_by_partner": true,
            "tags": [
                "Ácido Acetilsalicílico",
                "Aspirina Junior",
                "Indicado para aliviar el dolor de cabeza",
                "Algunas molestias del resfriado común, fiebre"
            ],
            "universal_product_id": "7501008494226"
        },
        {
            "_score": 89.17959,
            "_yscore": 0.7458811164749152,
            "byprice_uuid": "02a535a5-2ede-4877-82d7-88fdeae6f629",
            "image": [
                "https://byprice-item-images.s3-us-west-2.amazonaws.com/02a535a5-2ede-4877-82d7-88fdeae6f629/uploads/aspirina-protect-con-84-tabletas-100-mg-NID7fDoN7.jpg"
            ],
            "is_active": true,
            "is_prescription": false,
            "laboratories": [
                "Bayer"
            ],
            "name": "Aspirina Protect con 84 Tabletas (100 mg)",
            "names": [
                "aspirina protect 100 mg tab c84",
                "aspirina protect 100 mg tab c84",
                "aspirina protect 100 mg tab c84",
                "Aspirina Protect 84 Tabletas (100 mg)",
                "aspirina protect 100 mg caja con 84 tabletas de liberacion prolongada cardiovascular en mexico y df",
                "Aspirina Protect 84 Tabletas Ãcido AcetilsalicÃ­lico (100 mg)",
                "Aspirina Protect 100 mg 84 Tabletas - 3205",
                "Aspirina Protect 100 mg tabletas 84 pzas",
                "ASPIRINA PROTECT 100MG TAB CAJ C/84",
                "Aspirina Protec 100 mg con 84 tabletas",
                "Aspirina Protect 84 Tabletas Caja",
                "  Aspirina Protect 100 mg 84 tabletas",
                " Aspirina Protect 100mg 84 Tabletas Liberación Retardada"
            ],
            "product_uuid": null,
            "product_uuids": [
                "096cffc2-a208-47ff-915c-4c4aa4e719a6",
                "36cc5720-9243-4277-8dd0-9d3ea39b30ac",
                "8c326f78-eb3e-41ef-baa4-584c3f754b6e",
                "723fde26-dbb9-4e6d-a759-7120bc5eb270",
                "3a36bdc9-37cb-4647-b356-c0ab5c3baec8",
                "ec21995a-de4e-42d0-9c61-578b7c394568",
                "bdfbb0eb-42ab-4bfc-8e7a-50f52422cfc7",
                "89db108f-bac4-4488-9e99-d91a09dde4c9",
                "f184e60c-864d-11e9-8827-548ca04867a6",
                "82ec7aca-78c5-496e-b7cc-93d76000dcff",
                "8257aa1d-03e8-40bc-a9fb-fea1178dbc05",
                "4e238511-5439-449e-8c80-59a856e0ec9f",
                "a7526427-7fb6-49b6-b63f-01bded64846f"
            ],
            "retailers": [
                "fresko",
                "city_market",
                "la_comer",
                "rappi_benavides",
                "farmalisto",
                "farmazone",
                "gofarma",
                "superama",
                "farmacias_especializadas",
                "f_ahorro",
                "san_pablo",
                "walmart",
                "farmaciasguadalajara"
            ],
            "short_description": "Aspirina Protect con 84 Tabletas Ácido Acetilsalicílico (100 mg)",
            "sold_by_partner": true,
            "tags": [
                "Aspirina Protect",
                "Ácido Acetilsalicílico"
            ],
            "universal_product_id": "7501318673205"
        },

        {
            "_score": 71.10936,
            "_yscore": 0.5947451522104629,
            "byprice_uuid": null,
            "image": [
                "https://www.heb.com.mx/media/catalog/product/cache/3587d74c24c8bce0de8672583867fd28/5/3/532020_1732187617.jpg"
            ],
            "is_active": true,
            "is_prescription": false,
            "laboratories": [
                null
            ],
            "name": "Aspirina Protec 100 Mg 84 Tab Ac Acetilsalicilico 84 pz",
            "names": [],
            "product_uuid": "d69c1e75-3488-4c1e-964d-db53373e0043",
            "product_uuids": [],
            "retailers": [],
            "short_description": null,
            "sold_by_partner": false,
            "tags": [],
            "universal_product_id": null
        }
        ....
    ],
    "total": 17
}
```

## UUID -Search -API

#### Request

```
GET /search/uuid?q=523ee3bc-545e-4ecb-b78c-a582fd7ce682 HTTP/1.1
Host: localhost:8007
X-api-key: api_key
```

#### Parameters

| parameter | description   | mandatory | data type |
| --------- | ------------- | --------- | --------- |
| **q**     | uuid to query | must      | string    |

#### Response

Status: 200

```
{
    "filters": {},
    "items": [
        {
            "_score": 7.6566515,
            "_yscore": 0,
            "byprice_uuid": null,
            "image": [
                "https://ws.go-smart.com.mx/farmazone/imagenes/4005808571277.jpg"
            ],
            "is_active": true,
            "is_prescription": false,
            "laboratories": [
                null
            ],
            "name": "Nivea desmaquillante BifÃ¡sivo efecto dual 125 ml",
            "names": [],
            "product_uuid": "67cd433b-1f19-4c65-b8b0-8a5b15bec794",
            "product_uuids": [],
            "retailers": [],
            "short_description": "Nivea desmaquillante BifÃ¡sivo efecto dual 125 ml",
            "sold_by_partner": true,
            "tags": [],
            "universal_product_id": "4005808571277"
        }
    ],
    "total": 1
}
```


## Similar Products Recommendation -Search -API

#### Request

```
GET search/similar_products?qaspirin or lipitor&uuid=item_product_uuid&sold_by_partner=true HTTP/1.1
Host: localhost:8007
X-api-key: api_key
```

Notes
If you send uuid , I will only consider that, otherwise I will consider q

One of the two ( q , uuid) is must

#### Parameters

| parameter           | description              | mandatory | data type |
| ------------------- | ------------------------ | --------- | --------- |
| **q**               | name of the product/item | must      | string    |
| **uuid**            | uuid of the product/item | optional  | string    |
| **sold_by_partner** | filter                   | optional  | string    |

#### Response

Status: 200

```json
{
  "filters": {},
  "items": [
    {
      "_score": 94.43989,
      "_yscore": 0.9917085028864748,
      "byprice_uuid": "a7e28881-b73f-4edf-8d55-b15bb4105d34",
      "image": [
        "https://byprice-item-images.s3-us-west-2.amazonaws.com/a7e28881-b73f-4edf-8d55-b15bb4105d34/uploads/lipitor-con-15-tabletas-20-mg-dobRur66H.jpg"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Pfizer"],
      "name": "Lipitor con 15 Tabletas (20 mg)",
      "names": [
        "Lipitor 20 Mg. Oral 15 Tabletas",
        "  Lipitor 20 mg 15 tabletas",
        "Lipitor 20 Mg 15 Tab",
        "Lipitor 15 Tabletas (20 mg)",
        "lipitor 20 mg caja con 15 tabletas trigliceridos",
        "Lipitor 20 Mg. Oral 15 Tabletas",
        "LIPITOR 20MG TAB CAJ C/15",
        "LIPITOR 20 MG TAB 15",
        "Lipitor 15 Tabletas Atorvastatina (20 mg)"
      ],
      "product_uuid": null,
      "product_uuids": [
        "4767c8bb-9679-4373-9a5d-46fdf3f14d86",
        "f2c58fe4-e5c8-4c5f-8df5-60bac216a69d",
        "bcc11913-977d-4e1d-97e5-4c25da72c526",
        "1f5c46bb-4b3e-432c-8d2a-401f9211ed1d",
        "f5eb5e69-4655-457c-a63b-e6ae4d6bed1c",
        "876275c9-7237-4d74-9c5e-58d57558fad1",
        "ad9bb428-864f-11e9-8827-548ca04867a6",
        "7a5ea061-4f7b-43ba-847a-82017d5644be",
        "e9529bdb-203a-4501-9ba2-e4c4285a8f5d"
      ],
      "retailers": [
        "f_ahorro",
        "walmart",
        "cornershop",
        "rappi_benavides",
        "farmalisto",
        "f_ahorro",
        "farmacias_especializadas",
        "superama",
        "farmazone"
      ],
      "short_description": "Lipitor con 15 Tabletas Atorvastatina (20 mg)",
      "sold_by_partner": true,
      "tags": [
        "Lipitor ",
        "Atorvastatina ",
        "Tratamiento de pacientes con triglicéridos"
      ],
      "universal_product_id": "7501287640819"
    },
    {
      "_score": 89.17959,
      "_yscore": 0.9364703589439763,
      "byprice_uuid": "6ce565fd-85c6-475f-95be-b9b63d8a8378",
      "image": [
        "https://byprice-prod-images.s3-us-west-2.amazonaws.com/a7c5e8c2-6cd7-40b5-b1c8-63a911e38ae1/0.png"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Bayer"],
      "name": "Aspirina Advance con 20 Tabletas (500 mg)",
      "names": [
        "  Aspirina advanced 500 mg 20 tabletas",
        "Aspirina Advanced 20 Tabletas (500 mg)",
        "Aspirina Advanced 500 Mg Oral 20  Tabletas",
        "aspirina advance 500 mg caja con 20 tabletas",
        "aspirina advance analgesico 20 piezas",
        "Aspirina Advanced 500 mg 20 Tabletas - 8309",
        "Aspirina Advance 20 Tabletas Acido Acetilsalicilico (500 mg)",
        "Aspirina Advanced 20 Tabletas",
        "aspirina advanced",
        "ASPIRINA ADVANCE 500 MG C/20 TAB",
        "Aspirina  Advanced  500 Mg Bayer  20 Tab",
        "Aspirina Advanced",
        "aspirina advanced",
        "aspirina advanced"
      ],
      "product_uuid": null,
      "product_uuids": [
        "b77ab338-b4b2-4288-9a8f-7ca3e6b029ba",
        "30404f02-d6f6-453c-bba3-7216193e4308",
        "a7c5e8c2-6cd7-40b5-b1c8-63a911e38ae1",
        "f2dc1678-07ae-4328-bd44-c1358cdf06b8",
        "2e7e150e-047a-4d1c-9a66-b28f65c46b77",
        "198f0486-155d-4e38-8035-5caf0d87f04b",
        "8d945bab-c07c-4612-b8b7-ca1899565d91",
        "861453b4-1af3-4b4c-b41d-1b2c63dd6d19",
        "529bd485-91f7-4554-b852-9819a52ba50e",
        "be28f28c-494b-4191-9aca-056cebdc292c",
        "31327263-a0e2-4a6a-99ec-361a84c19db2",
        "3f9a4be3-911d-46de-af28-72a0917541b5",
        "c4f1dc25-2f2e-44c3-8532-b581ff08d3f5",
        "da7220ac-7d0c-4757-88c2-08d7bc4a3974"
      ],
      "retailers": [
        "walmart",
        "rappi_benavides",
        "f_ahorro",
        "farmalisto",
        "heb",
        "gofarma",
        "farmazone",
        "farmaciasguadalajara",
        "city_market",
        "farmatodo",
        "chedraui",
        "san_pablo",
        "la_comer",
        "fresko"
      ],
      "short_description": "Aspirina Advance con 20 Tabletas Ácido Acetilsalicílico (500 mg)",
      "sold_by_partner": true,
      "tags": [
        "Aspirina Advance",
        "Ácido Acetilsalicílico",
        "Alivio del dolor de cabeza, artritis, muelas",
        "Dolor muscular, dolor de oídos"
      ],
      "universal_product_id": "7501008498309"
    },
    {
      "_score": 89.17959,
      "_yscore": 0.9364703589439763,
      "byprice_uuid": "e57cb280-c959-48d2-8dbd-0120de954555",
      "image": [
        "https://byprice-prod-images.s3-us-west-2.amazonaws.com/928b6786-2403-4c9a-bcba-64994948f30d/0.png"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Bayer "],
      "name": "Aspirina Protect con 28 Tabletas (100 mg)",
      "names": [
        "aspirina protect 100 mg 28 tab",
        "Aspirina Protec 100 mg con 28 Tabletas",
        "Aspirina Protect 28 Tabletas Ãcido AcetilsalicÃ­lico (100 mg)",
        "aspirina protect 100 mg 28 tab",
        "Aspirina Protect 28 Tabs",
        "Aspirina PROTECT 100 mg con 28 tabletas",
        "Aspirina Protect 28 Tabletas (100 mg)",
        "aspirina-protec 100 miligramos 28 tabletas 28 piezas",
        "Aspirina Protect 100mg 28 Tabletas Liberación Retardada",
        "Aspirina Protect liberaci&#243;n prolongada 100 mg tabletas 28 pzas",
        "ASPIRINA PROTECT 100MG TAB CAJ C/28",
        "Aspirina Protect 28 Tabletas Caja",
        "aspirina protect 100 mg caja con 28 tabletas rx cardiovascular en mexico y df",
        "aspirina protect 100 mg 28 tab",
        "Aspirina Protect 100 mg 28 Tabletas - 2655",
        "  Aspirina Protect 100 mg 28 tabletas"
      ],
      "product_uuid": null,
      "product_uuids": [
        "882ef017-f7a2-42b6-af3b-3a236a48395b",
        "fb09e648-ef51-4737-a771-826cb57ec89f",
        "e9c4cb88-71aa-4f15-8503-c23d2c444753",
        "3b8e6660-0624-4f21-a749-278c2132a7ba",
        "b5834b74-363d-4645-b6af-f67e47254c15",
        "ceec2ee3-9f78-451e-adce-fecb0d69fb15",
        "f2a486bc-461b-4546-b77d-043518024597",
        "e7fd13f3-624d-4620-8d77-386e4b8bfdb6",
        "e89fe4a8-2f80-4334-9d4a-6648a47e0388",
        "928b6786-2403-4c9a-bcba-64994948f30d",
        "f14f14be-864d-11e9-8827-548ca04867a6",
        "e9aaeadd-c268-4781-b42d-1f298ace2fe6",
        "d0dea68d-0839-47ed-9349-0749061129d0",
        "1c465347-742f-416e-a420-e2cfc48ed5bf",
        "870ab899-f301-4a0c-8a3f-ed6fb86946fe",
        "830bb243-791c-49fc-9f38-22d138ec2099"
      ],
      "retailers": [
        "fresko",
        "f_ahorro",
        "farmazone",
        "city_market",
        "chedraui",
        "f_ahorro",
        "rappi_benavides",
        "heb",
        "farmaciasguadalajara",
        "superama",
        "farmacias_especializadas",
        "san_pablo",
        "farmalisto",
        "la_comer",
        "gofarma",
        "walmart"
      ],
      "short_description": "Aspirina Protect con 28 Tabletas Ácido Acetilsalicílico (100 mg)",
      "sold_by_partner": true,
      "tags": ["Ácido Acetilsalicílico", "Aspirina Protect "],
      "universal_product_id": "7501318612655"
    },
    {
      "_score": 89.17959,
      "_yscore": 0.9364703589439763,
      "byprice_uuid": "cb5cefd4-b741-4dc8-aaec-03fb021e571b",
      "image": [
        "https://byprice-prod-images.s3-us-west-2.amazonaws.com/41472704-7a3c-4f50-a053-0ab696ec4374/0.png"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Bayer"],
      "name": "Aspirina Junior con 60 Tabletas (100 mg)",
      "names": [
        "ASPIRINA JR 100MG TAB CAJ C/60",
        "aspirina t 60 100 mg jr",
        "aspirina t 60 100 mg jr",
        "aspirina t 60 100 mg jr",
        "aspirina junior 60 tab",
        "Aspirina Junior 60 Tabletas (100 mg)",
        "Aspirina Junior Analgésico 60 tabletas",
        "aspirina infantil 60 tab",
        "Aspirina Junior 60 Tabletas",
        "Aspirina Tabletas Junior, 100 mg",
        "Aspirina junior  60 tabletas",
        "aspirina junior 100 mg caja con 60 tabletas",
        "Aspirina Infantil C60 Tab",
        "Aspirina Junior 60 Tabletas",
        "Aspirina 100 Mg Oral Inf 60  Tabletas",
        "  Aspirina junior 100 mg 60 tabletas",
        "Aspirina Junior 100 mg 60 Tabletas - 4226",
        "Aspirina Para niño",
        "Aspirina Junior 60 Tabletas Acido Acetilsalicilico (100 mg)"
      ],
      "product_uuid": null,
      "product_uuids": [
        "f121f24a-864d-11e9-8827-548ca04867a6",
        "58e4b089-1771-46b1-b47b-85cec3e2c461",
        "4f90a1ba-d575-4e2b-b0a8-12d956a18b1c",
        "e94a2122-ac4e-4cf6-86fc-4216162e0678",
        "41472704-7a3c-4f50-a053-0ab696ec4374",
        "2d9b6803-014d-4f6d-a9c7-a80b0e81d6e8",
        "a795096b-e016-4521-b431-ec382f0a7880",
        "3b967938-2793-4fbf-a74f-c80771196e62",
        "ec7398c7-7b71-4d16-aa94-578d756aea6b",
        "42a4f5a0-ca83-44bd-9c0c-2b0a2b2b53a8",
        "1f1b9efc-4fed-4542-a99b-11d70c3c9353",
        "88c5916b-171f-4cd9-83a7-abfa958f3c9d",
        "afc44fa0-90ad-43b4-847c-96ddaed71972",
        "85ef4c05-041f-4576-a317-20a715b94cb4",
        "78cdcf1d-f363-44f8-a123-5c54fb5fb64a",
        "345c137a-251d-4035-bb43-1d28f0f0966a",
        "44542be0-370f-471c-a974-cf14ceb97751",
        "c6a67782-23a5-4686-bb5c-9f1f9842adf6",
        "8abe71c9-afbe-4d8f-bf90-eb9b07a18b70"
      ],
      "retailers": [
        "farmacias_especializadas",
        "la_comer",
        "city_market",
        "fresko",
        "superama",
        "rappi_benavides",
        "f_ahorro",
        "soriana",
        "farmaciasguadalajara",
        "amazon",
        "cornershop",
        "farmalisto",
        "chedraui",
        "sanborns",
        "f_ahorro",
        "walmart",
        "gofarma",
        "san_pablo",
        "farmazone"
      ],
      "short_description": "Aspirina Junior con 60 Tabletas Ácido Acetilsalicílico (100 mg)",
      "sold_by_partner": true,
      "tags": [
        "Ácido Acetilsalicílico",
        "Aspirina Junior",
        "Indicado para aliviar el dolor de cabeza",
        "Algunas molestias del resfriado común, fiebre"
      ],
      "universal_product_id": "7501008494226"
    },
    {
      "_score": 89.17959,
      "_yscore": 0.9364703589439763,
      "byprice_uuid": "02a535a5-2ede-4877-82d7-88fdeae6f629",
      "image": [
        "https://byprice-item-images.s3-us-west-2.amazonaws.com/02a535a5-2ede-4877-82d7-88fdeae6f629/uploads/aspirina-protect-con-84-tabletas-100-mg-NID7fDoN7.jpg"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Bayer"],
      "name": "Aspirina Protect con 84 Tabletas (100 mg)",
      "names": [
        "aspirina protect 100 mg tab c84",
        "aspirina protect 100 mg tab c84",
        "aspirina protect 100 mg tab c84",
        "Aspirina Protect 84 Tabletas (100 mg)",
        "aspirina protect 100 mg caja con 84 tabletas de liberacion prolongada cardiovascular en mexico y df",
        "Aspirina Protect 84 Tabletas Ãcido AcetilsalicÃ­lico (100 mg)",
        "Aspirina Protect 100 mg 84 Tabletas - 3205",
        "Aspirina Protect 100 mg tabletas 84 pzas",
        "ASPIRINA PROTECT 100MG TAB CAJ C/84",
        "Aspirina Protec 100 mg con 84 tabletas",
        "Aspirina Protect 84 Tabletas Caja",
        "  Aspirina Protect 100 mg 84 tabletas",
        " Aspirina Protect 100mg 84 Tabletas Liberación Retardada"
      ],
      "product_uuid": null,
      "product_uuids": [
        "096cffc2-a208-47ff-915c-4c4aa4e719a6",
        "36cc5720-9243-4277-8dd0-9d3ea39b30ac",
        "8c326f78-eb3e-41ef-baa4-584c3f754b6e",
        "723fde26-dbb9-4e6d-a759-7120bc5eb270",
        "3a36bdc9-37cb-4647-b356-c0ab5c3baec8",
        "ec21995a-de4e-42d0-9c61-578b7c394568",
        "bdfbb0eb-42ab-4bfc-8e7a-50f52422cfc7",
        "89db108f-bac4-4488-9e99-d91a09dde4c9",
        "f184e60c-864d-11e9-8827-548ca04867a6",
        "82ec7aca-78c5-496e-b7cc-93d76000dcff",
        "8257aa1d-03e8-40bc-a9fb-fea1178dbc05",
        "4e238511-5439-449e-8c80-59a856e0ec9f",
        "a7526427-7fb6-49b6-b63f-01bded64846f"
      ],
      "retailers": [
        "fresko",
        "city_market",
        "la_comer",
        "rappi_benavides",
        "farmalisto",
        "farmazone",
        "gofarma",
        "superama",
        "farmacias_especializadas",
        "f_ahorro",
        "san_pablo",
        "walmart",
        "farmaciasguadalajara"
      ],
      "short_description": "Aspirina Protect con 84 Tabletas Ácido Acetilsalicílico (100 mg)",
      "sold_by_partner": true,
      "tags": ["Aspirina Protect", "Ácido Acetilsalicílico"],
      "universal_product_id": "7501318673205"
    },
    {
      "_score": 88.440155,
      "_yscore": 0.9287055894505784,
      "byprice_uuid": "3f89369e-e0ad-498f-814d-f5556882ddff",
      "image": [
        "https://byprice-prod-images.s3-us-west-2.amazonaws.com/f874d8c1-af91-40c2-ae36-2f947d63f1d3/0.png"
      ],
      "is_active": true,
      "is_prescription": false,
      "laboratories": ["Pfizer"],
      "name": "Lipitor Duopack con 30 Tabletas (10 mg)",
      "names": [
        "lipitor 10 mg 11 caja c30 tab",
        "Lipitor Duopack 30 Tabletas Atorvastatina (10 mg)",
        "Lipitor 10Mg Caja Con 30 Tabletas",
        "lipitor 10 miligramos tabletas 30 11 461 30 piezas",
        "LIPITOR 10MG TAB DUO 2 CAJ C/30",
        "Lipitor 10mg 30 Tabletas 1+1 Promoción",
        "lipitor 10 mg 1+1 caja c30 tab",
        "lipitor 10 mg 1+1 caja c30 tab",
        "Lipitor 10 Mg. Oral 30 Tabletas 1+1",
        "Lipitor 11 30 Tabletas Caja",
        "  Lipitor 10 mg 2 cajas de 30 tabletas c/u",
        "Lipitor 1+1 10 mg 30 Tabletas - 0949",
        "Lipitor  tabletas 30 pzas de 10 mg c/u",
        "Lipitor 30 Tab (40 mg)",
        "Lipitor 10 Mg. Oral 30 Tabletas 1+1",
        "Lipitor 10 mg Caja Con 30 Tabletas"
      ],
      "product_uuid": null,
      "product_uuids": [
        "6065b06f-5af5-497c-bb15-495e808df42b",
        "55f82888-8fe6-4953-9fc0-f0e43ce55387",
        "f69973ca-1d2e-4211-887b-e07514a079b0",
        "d684e57b-d3f4-4e23-9d12-897aaa1a8379",
        "ad6c6ab0-864f-11e9-8827-548ca04867a6",
        "c9f9c44f-33cf-469f-90a8-53647a3e40a9",
        "7f115fd9-abff-4ec1-96fe-d00bd6ecbce8",
        "2730e82a-d903-4eca-ac2c-ebe9b9fad6cb",
        "a1f6961a-8297-40e2-a0e6-01de74101d27",
        "62a6d44c-3fe3-4930-b20c-0bea986bcdb2",
        "fc225290-e8b6-4234-b909-9af1fa1068f1",
        "1484ae6e-24a9-46de-9159-cfe93586d7ea",
        "f874d8c1-af91-40c2-ae36-2f947d63f1d3",
        "021e9278-710e-42a8-8869-8518befe5d1a",
        "d5e88560-d62d-4eea-998c-186767b424c0",
        "4348bfbd-1c5f-4967-8f66-41f59e4b5a40"
      ],
      "retailers": [
        "city_market",
        "farmazone",
        "chedraui",
        "heb",
        "farmacias_especializadas",
        "farmaciasguadalajara",
        "la_comer",
        "fresko",
        "f_ahorro",
        "san_pablo",
        "walmart",
        "gofarma",
        "superama",
        "rappi_benavides",
        "f_ahorro",
        "farmalisto"
      ],
      "short_description": "Lipitor Duopack con 30 Tabletas Atorvastatina (10 mg)",
      "sold_by_partner": true,
      "tags": [
        "Atorvastatina",
        "Lipitor Duopack",
        "Pacientes con triglicéridos"
      ],
      "universal_product_id": "7501287640949"
    }
  ],
  "total": 16
}
```
