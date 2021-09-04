## List all Sales Orders


```shell
curl "https://v-factory.omniship.eu/api/portal/v1/sales_orders"
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
  "sales_orders": [
    {
      "created_at": "2021-09-03T14:14:39+00:00",
      "last_modified": "2021-09-03T14:14:39+00:00",
      "ignore_auto_number_generation": true,
      "sales_order_number": "#1234",
      "state": "new",
      "reference": null,
      "destination_address": {
        "company_name": null,
        "contact_name": "Jane Doe",
        "contact_email": "jane@example.eu",
        "contact_phone": "415-1234567",
        "line_1": "417 Melrose Place",
        "line_2": "FLOOR 5",
        "postal_code": "90210",
        "city": "Los Angeles",
        "state": "CA",
        "country": "US",
        "country_full": "United States",
        "eori_number": null,
        "vat_number": null
      },
      "products": [
        {
          "name": "testProduct",
          "sku": "test",
          "barcode": "234234",
          "description": "test",
          "sales_rate": 20,
          "weight": 200,
          "currency": "EUR",
          "stock": {
            "warehouse": null,
            "total_stock": 0,
            "reserved": 0,
            "backorders": 0,
            "picklists": 0,
            "errors": 0,
            "free": 0
          }
        }
      ],
      "carrier_code": "ASEND",
      "tracking_number": null,
      "shipment_date": null,
      "notes": null
    },
    {
      "created_at": "2021-08-11T16:07:55+00:00",
      "last_modified": "2021-08-11T16:07:55+00:00",
      "ignore_auto_number_generation": false,
      "sales_order_number": "O2021-000000002",
      "state": "new",
      "reference": null,
      "destination_address": {
        "company_name": null,
        "contact_name": "testName",
        "contact_email": null,
        "contact_phone": "234234234",
        "line_1": "Van Marsbergenstraat 53",
        "line_2": null,
        "postal_code": "2134 LV",
        "city": "Hoofddorp",
        "state": null,
        "country": "NL",
        "country_full": "Netherlands",
        "eori_number": null,
        "vat_number": null
      },
      "products": [
        {
          "name": "test Product",
          "sku": "test SKU",
          "barcode": null,
          "description": null,
          "sales_rate": 200,
          "weight": 200,
          "currency": "EUR",
          "stock": {
            "warehouse": null,
            "total_stock": 0,
            "reserved": 0,
            "backorders": 0,
            "picklists": 0,
            "errors": 0,
            "free": 0
          }
        }
      ],
      "carrier_code": "ASEND",
      "tracking_number": null,
      "shipment_date": null,
      "notes": null
    },
    {"..."},
    {"..."}
	]
}
```

This endpoint retrieves all Sales Orders.

### HTTP Request

<span class="http-verb get">GET</span> `https://v-factory.omniship.eu/api/portal/v1/sales_orders`

Query params | Type | Description
--------- | ------- | -----------
sales_order_number | <span class="type">string</span> | Sales Order Number provided when creating the order. If multiple, separate with a comma.
created_at_from | <span class="type">date</span> | Search for orders created since this date
created_at_till | <span class="type">date</span> | Search for orders created since this date
state | <span class="type">string</span> | Search by current status of the Order. valid options\: <code>new</code>, <code>created</code>, <code>processing</code>, <code>shipped</code> <code>pending</code>, <code>action</code>, <code>out_of_stock</code>, <code>error</code>
page | <span class="type">integer</span> | Which page number want to fetch, default: <code>1</code>
per_page | <span class="type">integer</span> | Number of Orders per page to fetch, default: <code>25</code>, max: <code>100</code>
