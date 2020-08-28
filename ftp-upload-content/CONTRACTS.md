## Setup

Please ask for FTP credentials from 
##### yogesh@byprice.com
or
##### oscar@byprice.com



## Rules

### Add/Update

#### 1. Please follow The filename structure

Upload Geoprices filename should be like geoprice_retailer_key_hh_dd_mm_yyyy.csv
e.g 
```

geoprice_retailerkey_20_19_08_2020.csv
geoprice_retailerkey_21_19_08_2020.csv
geoprice_retailerkey_22_19_08_2020.csv
geoprice_retailerkey_23_19_08_2020.csv
geoprice_retailerkey_00_20_08_2020.csv

```


Upload Catalog filename should be like catalog_retailerkey_hh_dd_mm_yyyy.csv
e.g 

```
catalog_retailerkey_20_19_08_2020.csv
catalog_retailerkey_21_19_08_2020.csv
catalog_retailerkey_22_19_08_2020.csv
catalog_retailerkey_23_19_08_2020.csv
catalog_retailerkey_00_20_08_2020.csv
```



#### 2. Please follow structure of files, the column names should be same

geoprice_retailerkey_hh_dd_mm_yyyy.csv
```
retailer_product_id,date,price,original_price,stock,promotion,store_id
```

catalog_retailerkey_hh_dd_mm_yyyy.csv
```
universal_product_id,universal_product_id_type,retailer_product_id,name,category1,category2,category3,category4,category5,brand,tags,short_description,long_description,retailer,seller,price,is_active,is_visible,is_centralized,is_online,retailer_product_url,is_prescription,image,video
```

#### 3. You can check results files to know about errors and success in uploads
```
geoprice_retailerkey_results_21_19_08_2020.csv
catalog_retailerkey_results_23_19_08_2020.csv
```

#### 4. The history of files would be deleted after every 5 days


#### 5. Please upload only changes, ByPrice process these files every hour. At 16th minute of every hour


#### 6. The price changes would be reflected immediately. The catalog changes might take max 1 day. 


### Delete

Please put is_active=false if you want to delete any product in the catalog
