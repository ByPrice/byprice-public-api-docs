### Catalog Retailer Product Model 

```
retailer_product_id varchar(255) NOT NULL,
-- Must
-- Identifier for the product for retailer

universal_product_id varchar(255) NULL DEFAULT NULL::character varying,
-- Must
-- gtin number , ean number  etc

universal_product_id_type universal_id_type_enum NULL,
-- Must
-- 'gtin', 'upc', 'ean', 'ispn',

name text NOT NULL,
-- Must
-- Name of the product

category1 category1_enum NOT NULL,
-- Must
-- First level Category of the product

category2 varchar(255) NOT NULL,
-- Must
-- Second Level category of the product

category3 varchar(255) NULL DEFAULT NULL::character varying,
category4 varchar(255) NULL DEFAULT NULL::character varying,
category5 varchar(255) NULL DEFAULT NULL::character varying,

brand varchar(255) NULL DEFAULT NULL::character varying,
-- Must

tags _varchar NULL DEFAULT NULL::character varying[],
-- Default empty , but try to encourage the retailer to provide this
-- seo , search tags for the product

short_description text NULL,
-- Must
-- Short desciption of the product

long_description text NULL,
-- Optional
-- COmplet descrition or content of the product

"attribute" jsonb NULL,
-- dictionary
-- For medicine
{
    key: value
    color: red or blue or green etc ,
    size: small or medium or large etc
}

retailer varchar(255) NOT NULL,
-- Must
-- retailer_key

laboratory varchar(255) NULL DEFAULT NULL::character varying,
-- Optional
-- Laboratory for that product ( lanoratory name )

seller varchar(255) NULL DEFAULT NULL::character varying,
-- Optional
-- Seller for that product ( seller name )

price numeric(8,2) NULL DEFAULT NULL::numeric,
-- Must
-- General Price of the product, will not actually used , only used for matching validation

is_active bool NULL DEFAULT true,
-- if the product would be active on website, put is_active=false if you want to delete the product

is_visible bool NULL DEFAULT true,
-- if the product would be visible on website, put is_visible=false if you want to stop showing that product on website

is_centralized bool NOT NULL,
-- the product has same price and stock on every store

is_online bool NOT NULL,
-- is the product avavilable online

retailer_product_url text NULL,
-- url if product is sold online anywhere

is_prescription 
-- if the product needs prescription to be sold

image array of strings,
-- Array of urls

video array of strings,
-- Array of urls

```

### Geoprice Model/Pricing, Stock, Promotion

``` 
retailer_product_id string
-- Must
-- Identifier for the product for retailer

date string
-- Must , ddmmyyyy
-- Example 31082020

price string
-- Must , x.yy
-- It will be shown on the website, final purchasing cost
-- Decimal place should not be more than 2 places

original_price string
-- Must , x.yy
-- Printed cost , or max cost
-- Decimal place should not be more than 2 places

stock string
-- Must
-- Rules
-1 means out of stock
0 means stock not known
greater than 0 means real stock 

promotion string
-- Optional 
-- Any promotion

store_id string
-- Must
-- For which store this price and stock is for

```