## Update a Product

```shell
curl "https://v-factory.omniship.eu/api/portal/v1/products/SKU991"
  -X PATCH
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "name": "Updated name",
        "sku": "UpdatedSKU",
        "description": "Updated description",
        "barcode": "Updated barcode",
        "weight": 12,
        "length": 10,
        "width": 2,
        "height": 3,
        "sales_rate": "30.20",
        "hs_code": "1231232",
        "country_of_origin": "SR"
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
  "id": "a59bd158-2efb-11eb-b2c7-095feaa89723",
  "name": "Updated name",
  "sku": "UpdatedSKU",
  "description": "Updated description",
  "barcode": "Updated barcode",
  "weight": 12,
  "length": 10,
  "width": 2,
  "height": 3,
  "sales_rate": 30.2,
  "hs_code": "1231232",
  "country_of_origin": "SR",
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
```

This endpoint updates a Product in V-Factory Portal.

### HTTP Request

<span class="http-verb patch">PATCH</span> `https://v-factory.omniship.eu/api/portal/v1/products/<SKU>`

### URL Parameters

Parameter | Description
--------- | -----------
SKU | The SKU of the <span class="object">Product</span> to update

### Arguments

Attribute | Type | Description
--------- | ----------- | ----------
name | <span class="type">string</span> | Name of the product.
sku | <span class="type">string</span> | The Stock Keeping Unit (SKU) of an product. This is unique for every product in the inventory.
description | <span class="type">string</span> | Description of the product.
barcode | <span class="type">string</span> | Barcode (usually GS1, EAN13 or UPC code).
weight | <span class="type">integer</span> | Weight of the product in grams.
length | <span class="type">integer</span> | Length of the product.
width | <span class="type">integer</span> | Width of the product.
height | <span class="type">integer</span> | Height of the product.
sales_rate | <span class="type">double</span> | Sales price of the product.
hs_code | <span class="type">string</span> | HS Code for customs.
country_of_origin | <span class="type">string</span> | Country of origin of the product for customs (needs to be ISO 3166 2-char code).

## Inactivate a Product

```shell
curl "https://v-factory.omniship.eu/api/portal/v1/products/SKU991/inactivate"
  -X POST
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 204 No Content
Content-Type:application/json;charset=UTF-8
```

This endpoint inactivates a Product. To be able to inactivate an Product the Product cannot have stock, be open
on a picklist or have backorders, otherwise you will get an error.

A Product can also be re-activated with <span class="http-verb post">POST</span> `https://v-factory.omniship.eu/api/portal/v1/products/<ID>/activate`

### HTTP Requests

<span class="http-verb post">POST</span> `https://v-factory.omniship.eu/api/portal/v1/products/<ID>/inactivate`

<span class="http-verb post">POST</span> `https://v-factory.omniship.eu/api/portal/v1/products/<ID>/activate`
