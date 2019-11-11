# Inbound stock <i class="label label-atum">ATUM</i> #

The inbound stock API allows you to view the products that are set within pending purchase orders.

## Product properties ##

| Attribute               | Type      | Description                                                                                                                                                                                                             |
|-------------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                    | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                           |
| `name`                  | string    | Product name. <i class="label label-info">read-only</i>                                                                                                                                                                 |
| `type`                  | string    | Product type. Options: `simple`, `grouped`, `external`, `variable`, `product-part`, `raw-material`, `variable-product-part` and `variable-raw-material`. Default is `simple`. <i class="label label-info">read-only</i> |
| `sku`                   | string    | Product's Stock Keeping Unit. <i class="label label-info">read-only</i>                                                                                                                                                 |
| `inbound_stock`         | number    | The quantity of the product set within the purchase order. <i class="label label-info">read-only</i>                                                                                                                    |
| `date_ordered`          | date-time | The date when the Purchase Order was created, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                         |
| `date_ordered_gmt`      | date-time | The date when the Purchase Order was created, as GMT. <i class="label label-info">read-only</i>                                                                                                                         |
| `date_expected`         | date-time | The date when the Purchase Order is expected, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                         |
| `date_expected_gmt`     | date-time | The date when the Purchase Order is expected, as GMT. <i class="label label-info">read-only</i>                                                                                                                         |
| `purchase_order`        | integer   | Unique identifier for the Purchase Order. <i class="label label-info">read-only</i>                                                                                                                                     |

## Retrieve a product ##

This API lets you retrieve and view a the inbound stock for a specific product by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inbound-stock/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inbound-stock/175 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inbound-stock/175")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inbound-stock/175')); ?>
```

```python
print(wcapi.get("atum/inbound-stock/175").json())
```

```ruby
woocommerce.get("atum/inbound-stock/175").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 175,
        "name": "Product Part 1",
        "type": "product-part",
        "sku": "PART1",
        "inbound_stock": 1,
        "date_ordered": "2019-04-30T15:17:00",
        "date_on_sale_from_gmt": "2019-04-30T13:17:00",
        "date_expected": "2019-04-30T13:20:00",
        "date_expected_gmt": "2019-04-30T11:20:00",
        "purchase_order": 843,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/175"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 175,
        "name": "Product Part 1",
        "type": "product-part",
        "sku": "PART1",
        "inbound_stock": 1,
        "date_ordered": "2018-10-26T12:16:00",
        "date_on_sale_from_gmt": "2018-10-26T10:16:00",
        "date_expected": "2018-10-26T11:21:00",
        "date_expected_gmt": "2018-10-26T09:21:00",
        "purchase_order": 618,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/175"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    }
]
```

## List all products ##

This API helps you to view all the products.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inbound-stock</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inbound-stock \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inbound-stock")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inbound-stock')); ?>
```

```python
print(wcapi.get("atum/inbound-stock").json())
```

```ruby
woocommerce.get("atum/inbound-stock").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 507,
        "name": "ABC 123 XPTO",
        "type": "simple",
        "sku": "",
        "inbound_stock": 5,
        "date_ordered": "2019-10-24T10:16:12",
        "date_on_sale_from_gmt": "2019-10-24T08:16:12",
        "date_expected": "2019-11-11T09:55:31",
        "date_expected_gmt": "2019-11-11T08:55:31",
        "purchase_order": 1927,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/507"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 23,
        "name": "Ship Your Idea 2 - Black",
        "type": "variation",
        "sku": "",
        "inbound_stock": 1,
        "date_ordered": "2019-10-24T10:16:12",
        "date_on_sale_from_gmt": "2019-10-24T08:16:12",
        "date_expected": "2019-11-11T09:55:31",
        "date_expected_gmt": "2019-11-11T08:55:31",
        "purchase_order": 1927,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/23"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 93,
        "name": "Woo Single #1",
        "type": "simple",
        "sku": "Back Orders",
        "inbound_stock": 2,
        "date_ordered": "2019-10-04T11:35:00",
        "date_on_sale_from_gmt": "2019-10-04T09:35:00",
        "date_expected": "2019-10-05T10:00:00",
        "date_expected_gmt": "2019-10-05T08:00:00",
        "purchase_order": 1841,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/93"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 23,
        "name": "Ship Your Idea 2 - Black",
        "type": "variation",
        "sku": "",
        "inbound_stock": 1,
        "date_ordered": "2019-10-04T11:35:00",
        "date_on_sale_from_gmt": "2019-10-04T09:35:00",
        "date_expected": "2019-10-05T10:00:00",
        "date_expected_gmt": "2019-10-05T08:00:00",
        "purchase_order": 1841,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/23"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 175,
        "name": "Product Part 1",
        "type": "product-part",
        "sku": "PART1",
        "inbound_stock": 1,
        "date_ordered": "2019-04-30T15:17:00",
        "date_on_sale_from_gmt": "2019-04-30T13:17:00",
        "date_expected": "2019-04-30T13:20:00",
        "date_expected_gmt": "2019-04-30T11:20:00",
        "purchase_order": 843,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/175"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 513,
        "name": "Variable Product Part 1 - Black",
        "type": "product-part-variation",
        "sku": "VPART1",
        "inbound_stock": 1,
        "date_ordered": "2019-04-30T15:17:00",
        "date_on_sale_from_gmt": "2019-04-30T13:17:00",
        "date_expected": "2019-04-30T13:20:00",
        "date_expected_gmt": "2019-04-30T11:20:00",
        "purchase_order": 843,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/513"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 507,
        "name": "ABC 123 XPTO",
        "type": "simple",
        "sku": "",
        "inbound_stock": 1,
        "date_ordered": "2019-03-21T12:55:00",
        "date_on_sale_from_gmt": "2019-03-21T11:55:00",
        "date_expected": "2019-03-12T12:56:00",
        "date_expected_gmt": "2019-03-12T11:56:00",
        "purchase_order": 709,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/507"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 90,
        "name": "Woo Album #3",
        "type": "simple",
        "sku": "WOO3",
        "inbound_stock": 1,
        "date_ordered": "2019-03-11T09:35:00",
        "date_on_sale_from_gmt": "2019-03-11T08:35:00",
        "date_expected": "2019-03-11T09:36:00",
        "date_expected_gmt": "2019-03-11T08:36:00",
        "purchase_order": 701,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/90"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    },
    {
        "id": 76,
        "name": "Woo Ninja",
        "type": "simple",
        "sku": "",
        "inbound_stock": 1,
        "date_ordered": "2019-03-11T09:27:00",
        "date_on_sale_from_gmt": "2019-03-11T08:27:00",
        "date_expected": "2019-03-11T09:27:31",
        "date_expected_gmt": "2019-03-11T08:27:31",
        "purchase_order": 698,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock/76"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inbound-stock"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter         | Type    | Description                                                                                                                                                                                                       |
|-------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`         | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                                      |
| `page`            | integer | Current page of the collection. Default is `1`.                                                                                                                                                                   |
| `per_page`        | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                                            |
| `search`          | string  | Limit results to those matching a string.                                                                                                                                                                         |
| `after`           | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                                       |
| `before`          | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                                      |
| `exclude`         | array   | Ensure result set excludes specific IDs.                                                                                                                                                                          |
| `include`         | array   | Limit result set to specific ids.                                                                                                                                                                                 |
| `offset`          | integer | Offset the result set by a specific number of items.                                                                                                                                                              |
| `order`           | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                                       |
| `orderby`         | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                                     |
| `include_po`      | array   | Limit result set to products with specified Purchase Order IDs. <i class="label label-atum">ATUM</i>                                                                                                              |
| `exclude_po`      | array   | Ensure result set excludes specific Purchasr Order IDs. <i class="label label-atum">ATUM</i>                                                                                                                      |
| `expected_after`  | string  | Limit response to purchase orders expected after a given ISO8601 compliant date. <i class="label label-atum">ATUM</i>                                                                                             |
| `expected_before` | string  | Limit response to purchase orders expected before a given ISO8601 compliant date. <i class="label label-atum">ATUM</i>                                                                                            |
