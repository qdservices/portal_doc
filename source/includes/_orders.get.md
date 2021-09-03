## Get a Sales Order

```shell
curl "https://v-factory.omniship.eu/api/portal/v1/sales_orders/O2021-000000001"
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
  "sales_order": {
    "created_at": "2021-08-11T16:03:28+00:00",
    "last_modified": "2021-08-11T16:09:09+00:00",
    "ignore_auto_number_generation": false,
    "sales_order_number": "O2021-000000001",
    "state": "action",
    "reference": null,
    "destination_address": {
      "company_name": null,
      "contact_name": "testName",
      "contact_email": null,
      "contact_phone": "2342342",
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
  }
}
```

This endpoint retrieves a specific Sales Order.

### HTTP Request

<span class="http-verb get">GET</span> `https://app.omniship.eu/api/portal/v1/sales_orders/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The Sales Order Number of the Sales Order
