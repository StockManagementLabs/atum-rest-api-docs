# Inventories #

<i class="label label-atum">ATUM</i> <i class="label label-addon">Multi-Inventory</i>

The ATUM inventories API allows you to create, view, update, and delete inventories.

## Inventory properties ##

| Attribute          | Type      | Description                                                                                                            |
|--------------------|-----------|------------------------------------------------------------------------------------------------------------------------|
| `id`               | integer   | Unique identifier for the inventory. <i class="label label-info">read-only</i>                                         |
| `product_id`       | integer   | The product ID this inventory is linked to. <i class="label label-info">read-only</i>                                  |
| `name`             | string    | The inventory name. <i class="label label-info">mandatory</i>                                                          |
| `priority`         | integer   | The priority index within the list of the product inventories' list.                                                   |
| `is_main`          | boolean   | Whether the current inventory is the main inventory.                                                                   |
| `inventory_date`   | date-time | The date the inventory was created, as GMT.                                                                            |
| `lot`              | string    | The LOT/BATCH number.                                                                                                  |
| `write_off`        | boolean   | Number of published products for the resource.                                                                         |
| `region`           | array     | If the region restriction mode is enabled, it'll show the list of countries or shipping zones linked to the inventory. |
| `location`         | array     | ATUM Location(s) linked to the inventory.                                                                              |
| `bbe_date`         | date-time | The Best-Before-Expiry date for the inventory, as GMT.                                                                 |
| `expiry_days`      | integer   | The expiry days before the BBE date when the product should go out of stock.                                           |
| `inbound_stock`    | number    | Inventory's inbound stock. <i class="label label-info">read-only</i>                                                   |
| `stock_on_hold`    | number    | Inventory's stock on hold. <i class="label label-info">read-only</i>                                                   |
| `sold_today`       | number    | Inventory units sold today. <i class="label label-info">read-only</i>                                                  |
| `sales_last_days`  | number    | Inventory sales the last 14 days. <i class="label label-info">read-only</i>                                            |
| `reserved_stock`   | number    | Inventory stock set 'reserved_stock' within Inventory Logs. <i class="label label-info">read-only</i>                  |
| `customer_returns` | number    | Inventory stock set as 'customer returns' within Inventory Logs. <i class="label label-info">read-only</i>             |
| `warehouse_damage` | number    | Stock set as 'warehouse damage' within Inventory Logs. <i class="label label-info">read-only</i>                       |
| `lost_in_post`     | number    | Stock set as 'lost in post' within Inventory Logs. <i class="label label-info">read-only</i>                           |
| `other_logs`       | number    | Stock set as 'other' within Inventory Logs. <i class="label label-info">read-only</i>                                  |
| `out_stock_days`   | integer   | The number of days that the product is Out of stock. <i class="label label-info">read-only</i>                         |
| `lost_sales`       | number    | Product lost sales. <i class="label label-info">read-only</i>                                                          |
| `update_date`      | date-time | Last date when the inventory data was calculated and saved for this product, as GMT.                                   |
| `meta_data`        | object    | Meta data. See [Inventories - Meta data properties](#inventories-meta-data-properties)       
                                                                                                          
### Inventories - Meta data properties ###

| Attribute             | Type     | Description                                             |
|-----------------------|----------|---------------------------------------------------------|
| `sku`                 | string   | Inventory's SKU.                                        |
| `manage_stock`        | boolean  | Whether the stock is being managed for the inventory.   |
| `stock_quantity`      | number   | Inventory's stock amount.                               |
| `backorders`          | boolean  | Whether the back orders are allowed.                    |
| `stock_status`        | string   | Inventory's stock status.                               |
| `supplier_id`         | integer  | Inventoy supplier's ID.                                 |
| `supplier_sku`        | string   | Inventory supplier's SKU.                               |
| `out_stock_threshold` | number   | Inventory's out of stock threshold.                     |
| `purchase_price`     | number    | Inventory's purchase price.                             |
| `price`              | number    | Inventory's price.                                      |
| `regular_price`      | number    | Inventory's regular price.                              |
| `sale_price`         | number    | Inventory's sale price.                                 |
| `date_on_sale_from`  | date-time | The date when starts the sale price, as GMT.            |
| `date_on_sale_to`    | date-time | The date when ends the sale price, as GMT.              |
| `out_stock_date`     | date-time | The date when the inventory run out of stock, as GMT.   |

## Create an inventory ##

This API helps you to create a new inventory to the spedified product.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/inventories</h6>
	</div>
</div>

> Example of how to create a product inventory:

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/507/inventories \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
    "name": "Inventory 1",
    "is_main": false,
    "meta_data": {
        "sku": "TEST1",
        "manage_stock": true,
        "stock_quantity": 10,
        "backorders": false,
        "stock_status": "in_stock",
        "purchase_price": 9.5,
        "price": 12,
        "regular_price": 12
    } 
}'
```

```javascript
const data = {
    name: 'Inventory 1',
    is_main: false,
    meta_data: {
        sku: 'TEST1',
        manage_stock: true,
        stock_quantity: 10,
        backorders: false,
        stock_status: 'in_stock',
        purchase_price: 9.5,
        price: 12,
        regular_price: 12
    } 
 };

WooCommerce.post("products/507/inventories", data)
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
  'name' => 'Inventory 1',
  	'is_main' => false,
  	'meta_data' => [
  		'sku' => 'TEST1',
  		'manage_stock' => true,
  		'stock_quantity' => 10,
  		'backorders' => false,
  		'stock_status' => 'in_stock',
  		'purchase_price' => 9.5,
  		'price' => 12,
  		'regular_price' => 12,
  	] 
];

print_r($woocommerce->post('products/507/inventories', $data));
?>
```

```python
data = {
  "name": "Inventory 1",
  "is_main": false,
  "meta_data": {
    "sku": "TEST1",
    "manage_stock": true,
    "stock_quantity": 10,
    "backorders": false,
    "stock_status": "in_stock",
    "purchase_price": 9.5,
    "price": 12,
    "regular_price": 12
  } 
}

print(wcapi.post("products/507/inventories", data).json())
```

```ruby
data = {
  name: "Inventory 1",
  is_main: false,
  meta_data: {
    sku: "TEST1",
    manage_stock: true,
    stock_quantity: 10,
    backorders: false,
    stock_status: "in_stock",
    purchase_price: 9.5,
    price: 12,
    regular_price: 12
  } 
}

woocommerce.post("products/507/inventories", data).parsed_response
```

> JSON response example:

```json
{
    "id": 208,
    "product_id": 507,
    "name": "Inventory 1",
    "priority": 0,
    "is_main": false,
    "inventory_date": "2020-09-01T09:16:19",
    "lot": "",
    "write_off": false,
    "region": "",
    "location": [],
    "bbe_date": null,
    "expiry_days": 0,
    "meta_data": {
        "sku": "TEST1",
        "manage_stock": true,
        "stock_quantity": 10,
        "backorders": "no",
        "stock_status": "instock",
        "supplier_id": "",
        "supplier_sku": "",
        "sold_individually": false,
        "out_stock_threshold": "",
        "purchase_price": "9.5",
        "price": "12",
        "regular_price": "12",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_to": null,
        "out_stock_date": null
    },
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories/208"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507"
            }
        ]
    }
}
```

## Retrieve an inventory ##

This API lets you retrieve an inventory by ID.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/inventories/&lt;inventory_id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/507/inventories/208 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/507/inventories/208")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/507/inventories/208')); ?>
```

```python
print(wcapi.get("products/507/inventories/208").json())
```

```ruby
woocommerce.get("products/507/inventories/208").parsed_response
```

> JSON response example:

```json
{
    "id": 208,
    "product_id": 507,
    "name": "Inventory 1",
    "priority": 0,
    "is_main": false,
    "inventory_date": "2020-09-01T09:16:19",
    "lot": "",
    "write_off": false,
    "region": "",
    "location": [],
    "bbe_date": null,
    "expiry_days": 0,
    "inbound_stock": "0",
    "stock_on_hold": 0,
    "sold_today": 0,
    "sales_last_days": 0,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "update_date": "2020-09-01T09:16:19",
    "meta_data": {
        "sku": "TEST1",
        "manage_stock": true,
        "stock_quantity": 10,
        "backorders": "no",
        "stock_status": "instock",
        "supplier_id": "",
        "supplier_sku": "",
        "sold_individually": false,
        "out_stock_threshold": "",
        "purchase_price": "9.5",
        "price": "12",
        "regular_price": "12",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_to": null,
        "out_stock_date": null
    },
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories/208"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507"
            }
        ]
    }
}
```

## List all the product inventories ##

This API lets you retrieve all the inventories for the specified product.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/507/inventories</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/507/inventories \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/507/inventories")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/507/inventories')); ?>
```

```python
print(wcapi.get("products/507/inventories").json())
```

```ruby
woocommerce.get("products/507/inventories").parsed_response
```

> JSON response example:

```json
[
    {
        "id": "55",
        "product_id": 507,
        "name": "Main Inventory",
        "priority": 0,
        "is_main": true,
        "inventory_date": "2019-09-11T10:26:00",
        "lot": "",
        "write_off": false,
        "region": "",
        "location": {
            "50": "madrid"
        },
        "bbe_date": null,
        "expiry_days": 0,
        "inbound_stock": "1",
        "stock_on_hold": 4,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 1,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2020-08-31T07:27:30",
        "meta_data": {
            "sku": "",
            "manage_stock": true,
            "stock_quantity": 22,
            "backorders": "no",
            "stock_status": "instock",
            "supplier_id": 399,
            "supplier_sku": "CRYPTO",
            "sold_individually": false,
            "out_stock_threshold": "",
            "purchase_price": "2",
            "price": "5.32",
            "regular_price": "5.32",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_to": null,
            "out_stock_date": null
        },
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507/inventories/55"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507"
                }
            ]
        }
    },
    {
        "id": "208",
        "product_id": 507,
        "name": "Inventory 1",
        "priority": 0,
        "is_main": false,
        "inventory_date": "2020-09-01T09:16:19",
        "lot": "",
        "write_off": false,
        "region": "",
        "location": [],
        "bbe_date": null,
        "expiry_days": 0,
        "inbound_stock": "0",
        "stock_on_hold": 0,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2020-09-01T09:16:19",
        "meta_data": {
            "sku": "TEST1",
            "manage_stock": true,
            "stock_quantity": 10,
            "backorders": "no",
            "stock_status": "instock",
            "supplier_id": "",
            "supplier_sku": "",
            "sold_individually": false,
            "out_stock_threshold": "",
            "purchase_price": "9.5",
            "price": "12",
            "regular_price": "12",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_to": null,
            "out_stock_date": null
        },
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507/inventories/208"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/507"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter           | Type    | Description                                                                                                                                 |
|---------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------|
| `after`             | string  | Limit response to resources created after a given ISO8601 compliant date.                                                                   |
| `before`            | string  | Limit response to resources created before a given ISO8601 compliant date.                                                                  |
| `exclude`           | array   | Ensure result set excludes specific IDs.                                                                                                    |
| `include`           | array   | Limit result set excludes specific IDs.                                                                                                     |
| `offset`            | integer | Offset the result set by a specific number of items.                                                                                        |
| `order`             | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `asc`.                                                  |
| `orderby`           | string  | Sort collection by object attribute. Options: `priority`, `inventory_date`, `id`, `name` and `bbe_date`. Default is `priority`.             |
| `name`              | string  | Limit result set to inventories with a specific name.                                                                                       |
| `exclude_write_off` | boolean | Exclude from result set the inventories that were marked as 'write off'. Default is `true`.                                                 |
| `lot`               | string  | Limit result set to inventories with the specified LOT/BATCH number.                                                                        |
| `countries`         | string  | If the country restriction mode is enabled, limit the result set to inventories linked to the specified country.                            |
| `shipping_zone`     | string  | If the shipping zone restriction mode is enabled, limit the result set to inventories linked to the specified shipping zone.                |

## List all the inventories ##

This API lets you retrieve all the inventories registered on the system.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inventories</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inventories \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inventories")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inventories')); ?>
```

```python
print(wcapi.get("atum/inventories").json())
```

```ruby
woocommerce.get("atum/inventories").parsed_response
```

> JSON response example:

```json
[
    {
        "id": "3",
        "product_id": 90,
        "name": "Custom Inventory",
        "priority": 5,
        "is_main": false,
        "inventory_date": "2018-10-25T10:10:00",
        "lot": "",
        "write_off": false,
        "region": "",
        "location": [],
        "bbe_date": null,
        "expiry_days": 0,
        "inbound_stock": "0",
        "stock_on_hold": 17,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2020-10-05T07:20:52",
        "meta_data": {
            "sku": "WOO3",
            "manage_stock": true,
            "stock_quantity": 3,
            "backorders": "no",
            "stock_status": "instock",
            "supplier_id": 399,
            "supplier_sku": "SUPSK1",
            "sold_individually": false,
            "out_stock_threshold": "",
            "purchase_price": "18.9",
            "price": "15.7",
            "regular_price": "15.7",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_to": null,
            "out_stock_date": null,
            "expired_stock": null
        },
        "_links": {
            "self": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/90/inventories/3"
                }
            ],
            "collection": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/90/inventories"
                }
            ],
            "up": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/90"
                }
            ]
        }
    },
    {
        "id": "7",
        "product_id": 83,
        "name": "Main Inventory",
        "priority": 0,
        "is_main": true,
        "inventory_date": "2018-10-25T10:10:24",
        "lot": "",
        "write_off": false,
        "region": "",
        "location": [],
        "bbe_date": "-0001-11-30T00:00:00",
        "expiry_days": 0,
        "inbound_stock": "0",
        "stock_on_hold": 0,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 108,
        "lost_sales": 0,
        "update_date": "2020-10-05T07:20:53",
        "meta_data": {
            "sku": "",
            "manage_stock": true,
            "stock_quantity": 0,
            "backorders": "no",
            "stock_status": "instock",
            "supplier_id": "",
            "supplier_sku": "",
            "sold_individually": false,
            "out_stock_threshold": 0,
            "purchase_price": "128",
            "price": "9",
            "regular_price": "9",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_to": null,
            "out_stock_date": "2020-06-18T09:08:57",
            "expired_stock": null
        },
        "_links": {
            "self": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/83/inventories/7"
                }
            ],
            "collection": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/83/inventories"
                }
            ],
            "up": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/83"
                }
            ]
        }
    },
    {
        "id": "10",
        "product_id": 37,
        "name": "Main Inventory",
        "priority": 0,
        "is_main": true,
        "inventory_date": "2018-06-06T10:14:00",
        "lot": "123456",
        "write_off": false,
        "region": "",
        "location": [],
        "bbe_date": null,
        "expiry_days": 0,
        "inbound_stock": "0",
        "stock_on_hold": 0,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 1,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2020-06-04T06:20:29",
        "meta_data": {
            "sku": "",
            "manage_stock": true,
            "stock_quantity": 2,
            "backorders": "no",
            "stock_status": "instock",
            "supplier_id": "",
            "supplier_sku": "",
            "sold_individually": false,
            "out_stock_threshold": "",
            "purchase_price": "5",
            "price": "12",
            "regular_price": "12",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_to": null,
            "out_stock_date": null,
            "expired_stock": null
        },
        "_links": {
            "self": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/37/inventories/10"
                }
            ],
            "collection": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/37/inventories"
                }
            ],
            "up": [
                {
                    "href": "http://example.com/wp-json/wc/v3/products/37"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter           | Type    | Description                                                                                                                                 |
|---------------------|---------|---------------------------------------------------------------------------------------------------------------------------------------------|
| `after`             | string  | Limit response to resources created after a given ISO8601 compliant date.                                                                   |
| `before`            | string  | Limit response to resources created before a given ISO8601 compliant date.                                                                  |
| `exclude`           | array   | Ensure result set excludes specific IDs.                                                                                                    |
| `include`           | array   | Limit result set excludes specific IDs.                                                                                                     |
| `offset`            | integer | Offset the result set by a specific number of items.                                                                                        |
| `page`              | integer | Current page of the collection. Default is `1`.                                                                                             |
| `per_page`          | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                      |
| `order`             | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `asc`.                                                  |
| `orderby`           | string  | Sort collection by object attribute. Options: `priority`, `inventory_date`, `id`, `name` and `bbe_date`. Default is `id`.                   |
| `name`              | string  | Limit result set to inventories with a specific name.                                                                                       |
| `exclude_write_off` | boolean | Exclude from result set the inventories that were marked as 'write off'. Default is `true`.                                                 |
| `lot`               | string  | Limit result set to inventories with the specified LOT/BATCH number.                                                                        |
| `countries`         | string  | If the country restriction mode is enabled, limit the result set to inventories linked to the specified country.                            |
| `shipping_zone`     | string  | If the shipping zone restriction mode is enabled, limit the result set to inventories linked to the specified shipping zone.                |
| `product`           | integer | Filter the results by the specified product ID.                                                                                             |
| `search`            | string  | Limit results to those matching a string.                                                                                                   |


## Update an inventory ##

This API lets you make changes to a product inventory.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/inventories/&lt;inventory_id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/products/507/inventories/208 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
   "meta_data": {
       "stock_quantity": 200
   } 
}'
```

```javascript
const data = {
    meta_data: {
        stock_quantity: 200
    } 
 };

WooCommerce.put("products/507/inventories/208", data)
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
    'meta_data' => [
        'stock_quantity' => 200,
    ]
];

print_r($woocommerce->put('products/507/inventories/208', $data));
?>
```

```python
data = {
   "meta_data": {
       "stock_quantity": 200
   } 
}

print(wcapi.put("products/507/inventories/208", data).json())
```

```ruby
data = {
   meta_data: {
       stock_quantity: 200
   } 
}

woocommerce.put("products/507/inventories/208", data).parsed_response
```

> JSON response example:

```json
{
    "id": 208,
    "product_id": 507,
    "name": "Inventory 1",
    "priority": 0,
    "is_main": false,
    "inventory_date": "2020-09-01T09:16:19",
    "lot": "",
    "write_off": false,
    "region": "",
    "location": [],
    "bbe_date": null,
    "expiry_days": 0,
    "meta_data": {
        "sku": "TEST1",
        "manage_stock": true,
        "stock_quantity": 200,
        "backorders": "no",
        "stock_status": "instock",
        "supplier_id": "",
        "supplier_sku": "",
        "sold_individually": false,
        "out_stock_threshold": "",
        "purchase_price": "9.5",
        "price": "12",
        "regular_price": "12",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_to": null,
        "out_stock_date": null
    },
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories/208"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507"
            }
        ]
    }
}
```

## Delete a product inventory ##

This API helps you delete a product inventory.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/inventories/&lt;inventory_id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/products/507/inventories/208?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("products/507/inventories/208", {
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
<?php print_r($woocommerce->delete('products/507/inventories/208', ['force' => true])); ?>
```

```python
print(wcapi.delete("products/507/inventories/208", params={"force": True}).json())
```

```ruby
woocommerce.delete("products/507/inventories/208", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 208,
    "product_id": 507,
    "name": "Inventory 1",
    "priority": 0,
    "is_main": false,
    "inventory_date": "2020-09-01T09:16:19",
    "lot": "",
    "write_off": false,
    "region": "",
    "location": [],
    "bbe_date": null,
    "expiry_days": 0,
    "meta_data": {
        "sku": "TEST1",
        "manage_stock": true,
        "stock_quantity": 200,
        "backorders": "no",
        "stock_status": "instock",
        "supplier_id": "",
        "supplier_sku": "",
        "sold_individually": false,
        "out_stock_threshold": "",
        "purchase_price": "9.5",
        "price": "12",
        "regular_price": "12",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_to": null,
        "out_stock_date": null
    },
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories/208"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/507"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                   |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |

## Batch update product inventories ##

This API helps you to batch create, update and delete multiple product inventories.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/inventories/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/507/inventories/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
    "create": [
        {
            "name": "TEST Batch Inventory",
            "is_main": false
        }
    ],
    "update": [
        {
            "id": 152,
            "meta_data": {
                "manage_stock": true,
                "stock_quantity": 20
            }
        }
    ],
    "delete": [ 210, 211 ]
}'
```

```javascript
const data = {
     create: [
         {
             name: 'TEST Batch Inventory',
             is_main: false
         }
     ],
     update: [
         {
             id: 152,
             meta_data: {
                 manage_stock: true,
                 stock_quantity: 20
             }
         }
     ],
     delete: [ 210, 211 ]
};

WooCommerce.post("products/507/inventories/batch", data)
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
          'name' => 'TEST Batch Inventory',
          'is_main' => false
        ],
    ],
    'update' => [
        [
            'id' => 152,
            'meta_data' => [
                'manage_stock' => true,
                'stock_quantity' => 20
            ],
        ],
    ],
    'delete' => [
        210, 211
    ]
];

print_r($woocommerce->post('products/507/inventories/batch', $data));
?>
```

```python
data = {
    "create": [
        {
            "name": "TEST Batch Inventory",
            "is_main": false
        }
    ],
    "update": [
        {
            "id": 152,
            "meta_data": {
                "manage_stock": true,
                "stock_quantity": 20
            }
        }
    ],
    "delete": [ 210, 211 ]
}

print(wcapi.post("products/507/inventories/batch", data).json())
```

```ruby
data = {
   create: [
       {
           name: "TEST Batch Inventory",
           is_main: false
       }
   ],
   update: [
       {
           id: 152,
           meta_data: {
               manage_stock: true,
               stock_quantity: 20
           }
       }
   ],
   delete: [ 210, 211 ]
}

woocommerce.post("products/507/inventories/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 212,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:11:31",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/212"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 152,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 1,
            "is_main": false,
            "inventory_date": "2019-06-11T10:08:00",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": {
                "53": "slovakia",
                "49": "valencia"
            },
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": true,
                "stock_quantity": 20,
                "backorders": "no",
                "stock_status": "instock",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "5",
                "price": "20",
                "regular_price": "20",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/152"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 210,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:10:02",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/210"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        },
        {
            "id": 211,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:10:05",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/211"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ]
}
```
## Batch update All inventories ##

This API helps you to batch create, update and delete multiple inventories at once and also mixing inventories from distinct products at the same time.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/inventories/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/inventories/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
    "create": [
        {
            "product_id": 2123,
            "name": "TEST Batch Inventory",
            "is_main": false
        }
    ],
    "update": [
        {
            "id": 152,
            "meta_data": {
                "manage_stock": true,
                "stock_quantity": 20
            }
        }
    ],
    "delete": [ 210, 211 ]
}'
```

```javascript
const data = {
     create: [
         {
            product_id: 2123,
             name: 'TEST Batch Inventory',
             is_main: false
         }
     ],
     update: [
         {
             id: 152,
             meta_data: {
                 manage_stock: true,
                 stock_quantity: 20
             }
         }
     ],
     delete: [ 210, 211 ]
};

WooCommerce.post("atum/inventories/batch", data)
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
          'product_id' => 2123,
          'name' => 'TEST Batch Inventory',
          'is_main' => false
        ],
    ],
    'update' => [
        [
            'id' => 152,
            'meta_data' => [
                'manage_stock' => true,
                'stock_quantity' => 20
            ],
        ],
    ],
    'delete' => [
        210, 211
    ]
];

print_r($woocommerce->post('atum/inventories/batch', $data));
?>
```

```python
data = {
    "create": [
        {
            "product_id": 2123,
            "name": "TEST Batch Inventory",
            "is_main": false
        }
    ],
    "update": [
        {
            "id": 152,
            "meta_data": {
                "manage_stock": true,
                "stock_quantity": 20
            }
        }
    ],
    "delete": [ 210, 211 ]
}

print(wcapi.post("atum/inventories/batch", data).json())
```

```ruby
data = {
   create: [
       {
           product_id: 2123,
           name: "TEST Batch Inventory",
           is_main: false
       }
   ],
   update: [
       {
           id: 152,
           meta_data: {
               manage_stock: true,
               stock_quantity: 20
           }
       }
   ],
   delete: [ 210, 211 ]
}

woocommerce.post("atum/inventories/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 212,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:11:31",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/212"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 152,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 1,
            "is_main": false,
            "inventory_date": "2019-06-11T10:08:00",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": {
                "53": "slovakia",
                "49": "valencia"
            },
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": true,
                "stock_quantity": 20,
                "backorders": "no",
                "stock_status": "instock",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "5",
                "price": "20",
                "regular_price": "20",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/152"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 210,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:10:02",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/210"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        },
        {
            "id": 211,
            "product_id": 507,
            "name": "TEST Batch Inventory",
            "priority": 0,
            "is_main": false,
            "inventory_date": "2020-09-01T11:10:05",
            "lot": "",
            "write_off": false,
            "region": "",
            "location": [],
            "bbe_date": null,
            "expiry_days": 0,
            "meta_data": {
                "sku": "",
                "manage_stock": false,
                "stock_quantity": null,
                "backorders": "no",
                "stock_status": "",
                "supplier_id": "",
                "supplier_sku": "",
                "sold_individually": false,
                "out_stock_threshold": "",
                "purchase_price": "",
                "price": "",
                "regular_price": "",
                "sale_price": "",
                "date_on_sale_from": null,
                "date_on_sale_to": null,
                "out_stock_date": null
            },
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories/211"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507/inventories"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ]
            }
        }
    ]
}
```
