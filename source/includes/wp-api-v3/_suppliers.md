# Suppliers #

<i class="label label-atum">ATUM</i>

The suppliers API allows you to create, view, update, and delete individual, or a batch, of suppliers.

## Supplier properties ##

| Attribute               | Type      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                    | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `name`                  | string    | Supplier name.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `slug`                  | string    | Supplier slug.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `permalink`             | string    | Supplier URL. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `date_created`          | date-time | The date the supplier was created, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `date_created_gmt`      | date-time | The date the supplier was created, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `date_modified`         | date-time | The date the supplier was last modified, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `date_modified_gmt`     | date-time | The date the supplier was last modified, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `status`                | string    | Supplier status (post status). Options: `draft`, `pending`, `private` and `publish`. Default is `publish`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `code`                  | string    | Supplier code.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `tax_number`            | string    | Supplier tax/VAT number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `phone`                 | string    | Supplier phone number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `fax`                   | string    | Supplier fax number.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `website`               | string    | Supplier website.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `ordering_url`          | string    | Supplier ordering URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `general_email`         | string    | Supplier general email.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `ordering_email`        | string    | Supplier ordering email.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `description`           | string    | Supplier description.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `currency`              | string    | Supplier currency, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`.                   |
| `address`               | string    | Supplier address.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `city`                  | string    | Supplier city.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `country`               | string    | Supplier country ISO 3166 code. See [ISO 3166 Codes (Countries)](http://kirste.userpage.fu-berlin.de/diverse/doc/ISO_3166.html) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `state`                 | string    | Supplier state.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `zip_code`              | string    | Supplier ZIP code.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `assigned_to`           | integer   | The user ID that this supplier is assigned to.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `location`              | string    | The location used in Purchase Orders assigned to this supplier.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `images`                | object    | Supplier featured image. See [Supplier - Image properties](#supplier-image-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `meta_data`             | array     | Meta data. See [Supplier - Meta data properties](#supplier-meta-data-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

### Supplier - Image properties ###

| Attribute           | Type      | Description                                                                                             |
|---------------------|-----------|---------------------------------------------------------------------------------------------------------|
| `id`                | integer   | Image ID.                                                                                               |
| `date_created`      | date-time | The date the image was created, in the site's timezone. <i class="label label-info">read-only</i>       |
| `date_created_gmt`  | date-time | The date the image was created, as GMT. <i class="label label-info">read-only</i>                       |
| `date_modified`     | date-time | The date the image was last modified, in the site's timezone. <i class="label label-info">read-only</i> |
| `date_modified_gmt` | date-time | The date the image was last modified, as GMT. <i class="label label-info">read-only</i>                 |
| `src`               | string    | Image URL.                                                                                              |
| `name`              | string    | Image name.                                                                                             |
| `alt`               | string    | Image alternative text.                                                                                 |

### Supplier - Meta data properties ###

| Attribute | Type    | Description                                        |
|-----------|---------|----------------------------------------------------|
| `id`      | integer | Meta ID. <i class="label label-info">read-only</i> |
| `key`     | string  | Meta key.                                          |
| `value`   | string  | Meta value.                                        |

## Create a supplier ##

This API helps you to create a new supplier.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/suppliers</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/suppliers \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "name": "Supplier REST",
      "code": "4675763",
      "tax_number": "ES7667858Y",
      "phone": "+3412345678",
      "website": "https://example.com",
      "currency": "EUR",
      "address": "5th Avenue",
      "city": "London",
      "country": "GB",
      "assigned_to": 1,
      "location": "United Kingdom"
    }'
```

```javascript
const data = {
   name: "Supplier REST",
   code: "4675763",
   tax_number: "ES7667858Y",
   phone: "+3412345678",
   website: "https://example.com",
   currency: "EUR",
   address: "5th Avenue",
   city: "London",
   country: "GB",
   assigned_to: 1,
   location: "United Kingdom"
};

WooCommerce.post("atum/suppliers", data)
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$data = [
  'name' => 'Supplier REST',
  'code' => "4675763",
  'tax_number' => 'ES7667858Y',
  'phone' => '+3412345678',
  'website' => 'https://example.com',
  'currency' => 'EUR',
  'address' => '5th Avenue',
  'city' => 'London',
  'country' => 'GB',
  'assigned_to' => 1,
  'location' => 'United Kingdom'
];

print_r($woocommerce->post('atum/suppliers', $data));
?>
```

```python
data = {
 "name": "Supplier REST",
 "code": "4675763",
 "tax_number": "ES7667858Y",
 "phone": "+3412345678",
 "website": "https://example.com",
 "currency": "EUR",
 "address": "5th Avenue",
 "city": "London",
 "country": "GB",
 "assigned_to": 1,
 "location": "United Kingdom"
}

print(wcapi.post("atum/suppliers", data).json())
```

```ruby
data = {
 name: "Supplier REST",
 code: "4675763",
 tax_number: "ES7667858Y",
 phone: "+3412345678",
 website: "https://example.com",
 currency: "EUR",
 address: "5th Avenue",
 city: "London",
 country: "GB",
 assigned_to: 1,
 location: "United Kingdom"
}

woocommerce.post("atum/suppliers", data).parsed_response
```

> JSON response example:

```json
{
    "id": 2159,
    "name": "Supplier REST",
    "slug": "supplier-rest",
    "permalink": "https://example.com/?post_type=atum_supplier&p=2159",
    "date_created": "2019-11-12T12:34:38",
    "date_created_gmt": "2019-11-12T11:34:38",
    "date_modified": "2019-11-12T12:34:38",
    "date_modified_gmt": "2019-11-12T11:34:38",
    "status": "publish",
    "code": "4675763",
    "tax_number": "ES7667858Y",
    "phone": "+3412345678",
    "website": "https://example.com",
    "currency": "EUR",
    "address": "5th Avenue",
    "city": "London",
    "country": "GB",
    "assigned_to": "1",
    "location": "United Kingdom",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers/2159"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
            }
        ]
    }
}
```

## Retrieve a supplier ##

This API lets you retrieve and view a specific supplier by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/suppliers/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/suppliers/399 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/suppliers/399")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/suppliers/399')); ?>
```

```python
print(wcapi.get("atum/suppliers/399").json())
```

```ruby
woocommerce.get("atum/suppliers/399").parsed_response
```

> JSON response example:

```json
{
    "id": 399,
    "name": "Supplier 2",
    "slug": "supplier-2",
    "permalink": "https://example.com/?post_type=atum_supplier&p=399",
    "date_created": "2017-10-10T16:39:31",
    "date_created_gmt": "2017-10-10T15:39:31",
    "date_modified": "2017-10-10T17:39:58",
    "date_modified_gmt": "2017-10-10T16:39:58",
    "status": "publish",
    "code": "56498498",
    "tax_number": "959+58548",
    "phone": "98498498",
    "currency": "EUR",
    "country": "ES",
    "state": "Valencia",
    "assigned_to": "1",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers/399"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
            }
        ]
    }
}
```

## List all suppliers ##

This API helps you to view all the suppliers.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/suppliers</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/suppliers \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/suppliers")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/suppliers')); ?>
```

```python
print(wcapi.get("atum/suppliers").json())
```

```ruby
woocommerce.get("atum/suppliers").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 2159,
        "name": "Supplier REST",
        "slug": "supplier-rest",
        "permalink": "https://example.com/?post_type=atum_supplier&p=2159",
        "date_created": "2019-11-12T12:34:38",
        "date_created_gmt": "2019-11-12T11:34:38",
        "date_modified": "2019-11-12T12:34:38",
        "date_modified_gmt": "2019-11-12T11:34:38",
        "status": "publish",
        "code": "4675763",
        "tax_number": "ES7667858Y",
        "phone": "+3412345678",
        "website": "https://example.com",
        "currency": "EUR",
        "address": "5th Avenue",
        "city": "London",
        "country": "GB",
        "assigned_to": "1",
        "location": "United Kingdom",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers/2159"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                }
            ]
        }
    },
    {
        "id": 545,
        "name": "BOM Supplier",
        "slug": "bom-supplier",
        "permalink": "https://example.com/?post_type=atum_supplier&p=545",
        "date_created": "2018-06-11T07:14:58",
        "date_created_gmt": "2018-06-11T06:14:58",
        "date_modified": "2019-09-27T12:30:30",
        "date_modified_gmt": "2019-09-27T10:30:30",
        "status": "publish",
        "code": "854984984",
        "tax_number": "85489489",
        "currency": "BTC",
        "country": "CU",
        "assigned_to": "1",
        "image": {
            "id": 69,
            "date_created": "2013-06-07T13:22:05",
            "date_created_gmt": "2013-06-07T11:22:05",
            "date_modified": "2013-06-07T13:22:05",
            "date_modified_gmt": "2013-06-07T11:22:05",
            "src": "https://example.com/wp-content/uploads/2013/06/Poster_1_flat.jpg",
            "name": "Poster_1_flat",
            "alt": ""
        },
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers/545"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                }
            ]
        }
    },
    {
        "id": 426,
        "name": "New Supplier",
        "slug": "newsupplier",
        "permalink": "https://example.com/?post_type=atum_supplier&p=426",
        "date_created": "2018-01-10T15:58:10",
        "date_created_gmt": "2018-01-10T15:58:10",
        "date_modified": "2018-01-17T07:56:11",
        "date_modified_gmt": "2018-01-17T07:56:11",
        "status": "publish",
        "code": "AAABBB",
        "tax_number": "1234567",
        "phone": "321654",
        "currency": "ARS",
        "address": "Elm Street, 19",
        "city": "Madrid",
        "country": "ES",
        "state": "Madrid",
        "zip_code": "24001",
        "assigned_to": "1",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers/426"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                }
            ]
        }
    },
    {
        "id": 399,
        "name": "Supplier 2",
        "slug": "supplier-2",
        "permalink": "https://example.com/?post_type=atum_supplier&p=399",
        "date_created": "2017-10-10T16:39:31",
        "date_created_gmt": "2017-10-10T15:39:31",
        "date_modified": "2017-10-10T17:39:58",
        "date_modified_gmt": "2017-10-10T16:39:58",
        "status": "publish",
        "code": "56498498",
        "tax_number": "959+58548",
        "phone": "98498498",
        "currency": "EUR",
        "country": "ES",
        "state": "Valencia",
        "assigned_to": "1",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers/399"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter         | Type    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------    |---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`         | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `page`            | integer | Current page of the collection. Default is `1`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `per_page`        | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `search`          | string  | Limit results to those matching a string.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `after`           | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `before`          | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `modified_after`  | string  | Limit response to resources modified after a given ISO8601 compliant date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `modified_before` | string  | Limit response to resources modified before a given ISO8601 compliant date.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `exclude`         | array   | Ensure result set excludes specific IDs.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `include`         | array   | Limit result set to specific ids.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `offset`          | integer | Offset the result set by a specific number of items.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `order`           | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `orderby`         | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `slug`            | string  | Limit result set to suppliers with a specific slug.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |    
| `status`          | string  | Limit result set to suppliers assigned a specific status. Options: `any`, `draft`, `pending`, `private` and `publish`. Default is `any`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `currency`        | string  | Limit result set to suppliers using the specified currency code, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`. |
| `country`         | string  | Limit result set to suppliers from the specified ISO 3166 country code. See [ISO 3166 Codes (Countries)](http://kirste.userpage.fu-berlin.de/diverse/doc/ISO_3166.html) for more details.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `assigned_to`     | integer | Limit result set to suppliers assigned to the specified user ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `product`         | integer | Limit result set to suppliers assigned to the specific product ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

## Update a supplier ##

This API lets you make changes to a supplier.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/atum/suppliers/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/atum/suppliers/399 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "country": "ES",
      "location": "Spain"
    }'
```

```javascript
const data = {
   country: "ES",
   location: "Spain"
};

WooCommerce.put("atum/suppliers/399", data)
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$data = [
  'country' => 'ES',
  'location' => 'Spain'
];

print_r($woocommerce->put('atum/suppliers/399', $data));
?>
```

```python
data = {
 "country": "ES",
 "location": "Spain"
}

print(wcapi.put("atum/suppliers/399", data).json())
```

```ruby
data = {
 country: "ES",
 location: "Spain"
}

woocommerce.put("atum/suppliers/399", data).parsed_response
```

> JSON response example:

```json
{
    "id": 399,
    "name": "Supplier 2",
    "slug": "supplier-2",
    "permalink": "https://example.com/?post_type=atum_supplier&p=399",
    "date_created": "2017-10-10T16:39:31",
    "date_created_gmt": "2017-10-10T15:39:31",
    "date_modified": "2019-11-12T13:26:49",
    "date_modified_gmt": "2019-11-12T12:26:49",
    "status": "publish",
    "code": "56498498",
    "tax_number": "959+58548",
    "phone": "98498498",
    "currency": "EUR",
    "country": "ES",
    "state": "Valencia",
    "assigned_to": "1",
    "location": "Spain",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers/399"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
            }
        ]
    }
}
```

## Delete a supplier ##

This API helps you delete a supplier.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/atum/suppliers/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/atum/suppliers/2159?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("atum/suppliers/2159", {
  force: true
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->delete('atum/suppliers/2159', ['force' => true])); ?>
```

```python
print(wcapi.delete("atum/suppliers/2159", params={"force": True}).json())
```

```ruby
woocommerce.delete("atum/suppliers/2159", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 2159,
    "name": "Supplier REST",
    "slug": "supplier-rest",
    "permalink": "https://example.com/?post_type=atum_supplier&p=2159",
    "date_created": "2019-11-12T12:34:38",
    "date_created_gmt": "2019-11-12T11:34:38",
    "date_modified": "2019-11-12T12:34:38",
    "date_modified_gmt": "2019-11-12T11:34:38",
    "status": "publish",
    "code": "4675763",
    "tax_number": "ES7667858Y",
    "phone": "+3412345678",
    "website": "https://example.com",
    "currency": "EUR",
    "address": "5th Avenue",
    "city": "London",
    "country": "GB",
    "assigned_to": "1",
    "location": "United Kingdom",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers/2159"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                                |
|-----------|--------|----------------------------------------------------------------------------|
| `force`   | string | Use `true` whether to permanently delete the supplier, Default is `false`. |

## Batch update suppliers ##

This API helps you to batch create, update and delete multiple suppliers.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/suppliers/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/suppliers/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "create": [
        {
          "name": "TEST Batch Supplier",
          "tax_number": "GB87263874"
        },
        {
          "name": "TEST Batch Supplier 2",
          "address": "Saints Street, 500"
        }
      ],
      "update": [
        {
          "id": 426,
          "code": "ABC123"
        }
      ],
      "delete": [
        1817
      ]
    }'
```

```javascript
const data = {
   create: [
     {
       name: "TEST Batch Supplier",
       tax_number: "GB87263874"
     },
     {
       name: "TEST Batch Supplier 2",
       address: "Saints Street, 500"
     }
   ],
   update: [
     {
       id: 426,
       code: "ABC123"
     }
   ],
   delete: [
     1817
   ]
};

WooCommerce.post("atum/suppliers/batch", data)
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$data = [
  'create' => [
    [
      'name' => 'TEST Batch Supplier',
      'tax_number' => 'GB87263874'
    ],
    [
      'name' => 'TEST Batch Supplier 2',
      'address' => 'Saints Street, 500'
    ]
  ],
  'update' => [
    [
      'id' => 426,
      'code' => 'ABC123'
    ]
  ],
  'delete' => [
    1817
  ]
];

print_r($woocommerce->post('atum/suppliers/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "name": "TEST Batch Supplier",
     "tax_number": "GB87263874"
   },
   {
     "name": "TEST Batch Supplier 2",
     "address": "Saints Street, 500"
   }
 ],
 "update": [
   {
     "id": 426,
     "code": "ABC123"
   }
 ],
 "delete": [
   1817
 ]
}

print(wcapi.post("atum/suppliers/batch", data).json())
```

```ruby
data = {
 create: [
   {
     name: "TEST Batch Supplier",
     tax_number: "GB87263874"
   },
   {
     name: "TEST Batch Supplier 2",
     address: "Saints Street, 500"
   }
 ],
 update: [
   {
     id: 426,
     code: "ABC123"
   }
 ],
 delete: [
   1817
 ]
}

woocommerce.post("atum/suppliers/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2161,
            "name": "TEST Batch Supplier",
            "slug": "test-batch-supplier",
            "permalink": "https://example.com/?post_type=atum_supplier&p=2161",
            "date_created": "2019-11-12T13:37:55",
            "date_created_gmt": "2019-11-12T12:37:55",
            "date_modified": "2019-11-12T13:37:55",
            "date_modified_gmt": "2019-11-12T12:37:55",
            "status": "publish",
            "tax_number": "GB87263874",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers/2161"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                    }
                ]
            }
        },
        {
            "id": 2162,
            "name": "TEST Batch Supplier 2",
            "slug": "test-batch-supplier-2",
            "permalink": "https://example.com/?post_type=atum_supplier&p=2162",
            "date_created": "2019-11-12T13:37:55",
            "date_created_gmt": "2019-11-12T12:37:55",
            "date_modified": "2019-11-12T13:37:55",
            "date_modified_gmt": "2019-11-12T12:37:55",
            "status": "publish",
            "address": "Saints Street, 500",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers/2162"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 426,
            "name": "New Supplier",
            "slug": "newsupplier",
            "permalink": "https://example.com/?post_type=atum_supplier&p=426",
            "date_created": "2018-01-10T15:58:10",
            "date_created_gmt": "2018-01-10T15:58:10",
            "date_modified": "2019-11-12T13:37:55",
            "date_modified_gmt": "2019-11-12T12:37:55",
            "status": "publish",
            "code": "ABC123",
            "tax_number": "1234567",
            "phone": "321654",
            "currency": "ARS",
            "address": "Elm Street, 19",
            "city": "Madrid",
            "country": "ES",
            "state": "Madrid",           
            "zip_code": "24001",
            "assigned_to": "1",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers/426"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 1817,
            "name": "REST old supplier",
            "slug": "rest-old-supplier",
            "permalink": "https://example.com/?post_type=atum_supplier&p=1817",
            "date_created": "2019-09-30T13:55:51",
            "date_created_gmt": "2019-09-30T11:55:51",
            "date_modified": "2019-09-30T13:55:51",
            "date_modified_gmt": "2019-09-30T11:55:51",
            "status": "publish",
            "code": "675675GQA",
            "currency": "EUR",
            "country": "ES",
            "assigned_to": "1",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers/1817"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/suppliers"
                    }
                ]
            }
        }
    ]
}
```
