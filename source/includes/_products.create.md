## Create a Product

```shell
curl "https://v-factory.omniship.eu/api/portal/v1/products"
  -X POST
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
          "sku": "SKU991",
          "name": "Shoes",
          "barcode": "153485909567",
          "description": "description",
          "weight": 250,
          "length": 10,
          "width": 5,
          "height": 2,
          "sales_rate": 19.81,
          "hs_code": "9876878",
          "country_of_origin": "NL",
          "unlimited_stock": false,
          "minimum_stock_level": 20,
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 201 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "product": {
    "id": "a59bd158-2efb-11eb-b2c7-095feaa89723",
    "name": "Shoes",
    "sku": "SKU991",
    "description": "description",
    "barcode": "153485909567",
    "weight": 250,
    "length": 10,
    "width": 5,
    "height": 2,
    "sales_rate": 19.81,
    "hs_code": "9876878",
    "country_of_origin": "NL",
    "active": true,
    "stock": [
      {
        "warehouse": "Main Warehouse",
        "total_stock": 0,
        "reserved": 0,
        "backorders": 0,
        "picklists": 0,
        "free": 0,
        "locations": []
      }
    ]
  }
}
```

### HTTP Request

<span class="http-verb post">POST</span> `https://v-factory.omniship.eu/api/portal/v1/products`

### Arguments

Attribute | Type | Description
--------- | ----------- | ----------
name | <span class="type">string</span> | <span class="required">Required</span> Name of the product.
sku | <span class="type">string</span> | <span class="required">Required</span> The Stock Keeping Unit (SKU) of an product. This is unique for every product in the inventory.
description | <span class="type">string</span> | <span class="optional">optional</span> Description of the product.
barcode | <span class="type">string</span> | <span class="optional">optional</span> Barcode (usually GS1, EAN13 or UPC code).
sales_rate | <span class="type">double</span> | <span class="required">required</span> Sales price of the product.
weight | <span class="type">integer</span> | <span class="optional">optional</span> Weight of the product in grams.
length | <span class="type">integer</span> | <span class="optional">optional</span> Length of the product in centimeters.
width | <span class="type">integer</span> | <span class="optional">optional</span> Width of the product in centimeters.
height | <span class="type">integer</span> | <span class="optional">optional</span> Height of the product in centimeters.
hs_code | <span class="type">string</span> | <span class="optional">optional</span> HS Code for customs.
country_of_origin | <span class="type">string</span> | <span class="optional">optional</span> Country of origin of the product for customs (needs to be ISO 3166 2-char code).
