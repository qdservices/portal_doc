## List all Products


```shell
curl "https://v-factory.omniship.eu/api/portal/v1/products"
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
	"products": [
    {
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
    },
    {"..."},
    {"..."}
	]
}
```

This endpoint retrieves all Products.

### HTTP Request

<span class="http-verb get">GET</span> `https://v-factory.omniship.eu/api/portal/v1/products`

Query params | Type | Description
--------- | ------- | -----------
SKU | <span class="type">string</span> | SKU provided when creating the product. If multiple, separate with a comma.
created_at_from | <span class="type">date</span> | Search for products created since this date
created_at_till | <span class="type">date</span> | Search for products created since this date
inactive | <span class="type">boolean</span> | Get the products that are inactive. Valid values are `true`, `false`. By default, only products with active state are returned. Set parameter to `false` to retrieve all products.
page | <span class="type">integer</span> | Which page number want to fetch, default: <code>1</code>
per_page | <span class="type">integer</span> | Number of Products per page to fetch, default: <code>25</code>, max: <code>100</code>
