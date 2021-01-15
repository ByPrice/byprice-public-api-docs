# Identity Services Endpoints

## Tu_Farmacia-API

### Fields/Data Model

**email**

- Data type: str, Must
- Description: Client Email 
- Validation: valid email
- Examples: yogesh@byprice.com | test@gmail.com

**first_name**

- Data type: str
- Description: Customer name
- Validation: No validation required
- Examples: "Yogesh" or "Yogesh Yadav"

### Partner user auth API

#### Request - All OK

```
POST /identity/tu_farmacia/customer_auth/authenticate_credential HTTP/1.1
Host: dev-api.byprice.com
X-api-key: byprice_own_key
Content-Type: application/json

{
    "email":"vofah99067@izzum.com",
    "first_name":"vofah"
}
```

#### Response

Status : 200

```
{
    "customer_uuid": "5b03557f-4f09-476a-9b91-ad9e9b91fd63",
    "expiration": 604800,
    "token": "eyJhbGciOiJIUzUxMiIsImlhdCI6MTYxMDY5OTk0NiwiZXhwIjoxNjExMzA0NzQ2fQ.eyJjdXN0b21lcl91dWlkIjoiNWIwMzU1N2YtNGYwOS00NzZhLTliOTEtYWQ5ZTliOTFmZDYzIn0.HR2Jm3Qk6NFUVtL_AE9vAdfKmEVmQzrvkt83nHjg2oq8V2UwKQpIlA-BPiaGlAY4W8gdHLPtA-wbenFyFhvHAQ"
}
```


#### Request - Error

```
POST /identity/tu_farmacia/customer_auth/authenticate_credential HTTP/1.1
Host: dev-api.byprice.com
X-api-key: byprice_own_key
Content-Type: application/json

{
    "email":"vofah99067@izzum",
    "first_name":"vofah"
}
```

#### Response

Status : 400

```
{
    "errors": [
        {
            "code": "RP007",
            "description": "Incorrect email",
            "message": "Invalid email"
        }
    ]
}
```