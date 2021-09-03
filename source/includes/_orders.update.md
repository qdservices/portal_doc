## Update a Sales Order

```shell
curl "https://v-factory.omniship.eu/api/portal/v1/sales_order/O2021-000000001"
  -X PATCH
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "destination_address": {
          "contact_name": "Elliot Alderson"
        }
      }'
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
      "contact_name": "Elliot Alderson",
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

This endpoint updates a Sales Order in V-factory. A <span class="object">Sales Order</span> can only be updated if not yet processed.

### HTTP Request

<span class="http-verb patch">PATCH</span> `https://v-factory.omniship.eu/api/portal/v1/sales_orders/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The Sales Order Number of the <span class="object">Sales Order</span> to update

### Arguments

Attribute | Type | Description
--------- | ----------- | ----------
reference | <span class="type">string</span> | Reference information that prints on the shipping label (if courier allows it).
destination_address | <span class="type">object</span> | <span class="object">Address</span> object that should be used as the receiver address.
products | <span class="type">array</span> | <span class="required">required</span> Array of <span class="object">Product</span> objects. Each line item contains the item `sku`, and `quantity` (quantity of the product for the order).
carrier | <span class="type">string</span> | <span class="optional">optional</span> Select a specific couriers <code>admin_name</code> to create the shipment with. Use the <a href="#couriers">Couriers API</a> resource to retrieve a list of available couriers and their admin names.
notes | <span class="type">string</span> | <span class="optional">optional</span> Notes for the Sales Order.

### Address Object definitions:

<div class="magic-block-parameters">
	<div class="block-parameters-table">
		<div class="table">
			<div class="tr">
				<div class="th" style="min-width: 120px;">Field Name</div>
				<div class="th">Type</div>
				<div class="th">Description</div>
			</div>
			<div class="tr">
				<div class="td"><p><code>contact_name</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address contact name. Maximum: 35 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>company_name</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address company name. Maximum: 35 characters </p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>contact_email</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address contact email address. Maximum: 50 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>contact_phone</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address contact phone number. Maximum: 18 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>line_1</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address line 1. Maximum: 35 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>line_2</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address line 2. Maximum: 35 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>postal_code</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required_if">required if</span> Country is postal aware. Address postal code. </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>city</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address city</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>state</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required_if">required if</span> Country has states. (US, CA, MX, IN)</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>country</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Address country code in Alpha 2 Format  (ISO 3166-1)</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>eori_number</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>Economic Operators Registration and Identification (EORI) number</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>vat_number</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p>The consignee's tax identification number</p></div>
			</div>
		</div>
	</div>
</div>

### Product definitions:

<div class="magic-block-parameters">
	<div class="block-parameters-table">
		<div class="table">
			<div class="tr">
				<div class="th" style="min-width: 120px;">Field Name</div>
				<div class="th">Type</div>
				<div class="th">Description</div>
			</div>
      <div class="tr">
				<div class="td"><p><code>sku</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required_if">required when</span> updating an existing <span class="object">Product</span> object. SKU of the object updating.</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>quantity</code></p></div>
				<div class="td"><p><span>integer</span></p></div>
				<div class="td"><p><span class="optional">optional</span> The quantity of parcels with the same measures. Default is <code>1</code></p></div>
			</div>
		</div>
	</div>
</div>
