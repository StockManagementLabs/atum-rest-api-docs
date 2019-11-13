# Dashboard #

The dashboard API allows you to get all types of ATUM Dashboard widgets available.

## List all widgets ##

This API lets you retrieve and view a simple list of available widgets.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/dashboard')); ?>
```

```python
print(wcapi.get("atum/dashboard").json())
```

```ruby
woocommerce.get("atum/dashboard").parsed_response
```

> JSON response example:

```json
[
    {
        "slug": "statistics",
        "description": "Displays both: your earnings and product sales over time.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/statistics"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "sales",
        "description": "Displays all of your sales and number of products sold by day or month.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/sales"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "lost-sales",
        "description": "Displays all of your lost revenue and number of products not sold by day or month.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/lost-sales"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "orders",
        "description": "Displays all of your orders by day, week or month.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/orders"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "promo-sales",
        "description": "Displays all of your promo sales and number of promo products sold by day, week or month.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/promo-sales"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "stock-control",
        "description": "Displays the number of your products that are in stock, out of stock, running low and unmanaged.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/stock-control"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    },
    {
        "slug": "current-stock-value",
        "description": "Displays the total quantity of items physically in stock (that have known purchase price) and their cumulated purchase value.",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard/current-stock-value"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

## Retrieve statistics widget data ##

This API lets you retrieve and view the Dashboard's statistics widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dasboard/statistics</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/statistics?data=sales&period=this_year \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/statistics", {
  data: "sales",
  period: "this_year"
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$query = [
    'data' => 'sales', 
    'period' => 'this_year'
];

print_r($woocommerce->get('atum/dashboard/statistics', $query));
?>
```

```python
print(wcapi.get("atum/dashboard/statistics?data=sales&period=this_year").json())
```

```ruby
query = {
  data: "sales",
  period: "this_year"
}

woocommerce.get("atum/dashboard/statistics", query).parsed_response
```

> JSON response example:

```json
[
    {
        "dataset": {
            "value": [
                75,
                838.7,
                0,
                643.7,
                48,
                0,
                0,
                0,
                210,
                102,
                0
            ],
            "products": [
                6,
                74,
                0,
                80,
                4,
                0,
                0,
                0,
                9,
                17,
                0
            ]
        },
        "legends": {
            "value": "Sales",
            "products": "Products"
        },
        "period": "month",
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Statistics widget properties ####

| Attribute | Type    | Description                                                                                                                    |
|-----------|---------|--------------------------------------------------------------------------------------------------------------------------------|
| `dataset` | object  | The collection of data for the statistics. It contains `value` and `products` data. <i class="label label-info">read-only</i>  |
| `period`  | string  | The period window used to get the statistics for. <i class="label label-info">read-only</i>                                    |
| `legends` | object  | The legends used on the statistics charts. <i class="label label-info">read-only</i>                                           |

#### Available parameters ####

| Parameter  | Type   | Description                                                                                                                                                         |
|------------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `data`  | string | The type of data to return. Default is `sales`. Options: `sales`, `lost-sales`, `promo-sales` and `orders`.                                                            |
| `period`   | string | The period to get statistics from. Default is `this_year`. Options: `this_year`, `previous_year`, `this_month`, `previous_month`, `this_week` and `previous_week`.  |

## Retrieve sales widget data ##

This API lets you retrieve and view the Dashboard's sales widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/sales</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/sales?period=month \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/sales", {
  period: "month"
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$query = [
    'period' => 'month'
];

print_r($woocommerce->get('atum/dashboard/sales', $query));
?>
```

```python
print(wcapi.get("atum/dashboard/sales?period=month").json())
```

```ruby
query = {
  period: "month"
}

woocommerce.get("atum/dashboard/sales", query).parsed_response
```

> JSON response example:

```json
[
    {
        "period": "month",
        "data": {
            "value": "&euro;1590,00",
            "products": 12
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Sales widget properties ####

| Attribute | Type    | Description                                                                                  |
|-----------|---------|----------------------------------------------------------------------------------------------|
| `period`  | string  | The period window used to get the sales data for. <i class="label label-info">read-only</i> |
| `data`    | object | The sales data. It contains `value` and `products` data. <i class="label label-info">read-only</i>  |

#### Available parameters ####

| Parameter  | Type   | Description                                                                         |
|------------|--------|-------------------------------------------------------------------------------------|
| `period`   | string | The period to get sales data from. Default is `today`. Options: `today` and `month` |

## Retrieve lost sales widget data ##

This API lets you retrieve and view the Dashboard's lost sales widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/lost-sales</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/lost-sales?period=month \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/lost-sales", {
  period: "month"
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$query = [
    'period' => 'month'
];

print_r($woocommerce->get('atum/dashboard/lost-sales', $query));
?>
```

```python
print(wcapi.get("atum/dashboard/lost-sales?period=month").json())
```

```ruby
query = {
  period: "month"
}

woocommerce.get("atum/dashboard/lost-sales", query).parsed_response
```

> JSON response example:

```json
[
    {
        "period": "month",
        "data": {
            "value": "&euro;0,00",
            "products": 12
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Lost sales widget properties ####

| Attribute | Type   | Description                                                                                              |
|-----------|--------|----------------------------------------------------------------------------------------------------------|
| `period`  | string | The period window used to get the lost sales data for. <i class="label label-info">read-only</i>         |
| `data`    | object | The lost sales data. It contains `value` and `products` data. <i class="label label-info">read-only</i>  |

#### Available parameters ####

| Parameter  | Type   | Description                                                                              |
|------------|--------|------------------------------------------------------------------------------------------|
| `period`   | string | The period to get lost sales data from. Default is `today`. Options: `today` and `month` |

## Retrieve orders widget data ##

This API lets you retrieve and view the Dashboard's orders widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/orders</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/orders?period=previous_month \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/orders", {
  period: "previous_month"
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$query = [
    'period' => 'previous_month'
];

print_r($woocommerce->get('atum/dashboard/orders', $query));
?>
```

```python
print(wcapi.get("atum/dashboard/orders?period=previous_month").json())
```

```ruby
query = {
  period: "previous_month"
}

woocommerce.get("atum/dashboard/orders", query).parsed_response
```

> JSON response example:

```json
[
    {
        "period": "previous_month",
        "data": {
            "value": "&euro;16.121,98",
            "orders": 137
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Orders widget properties ####

| Attribute | Type   | Description                                                                                          |
|-----------|--------|------------------------------------------------------------------------------------------------------|
| `period`  | string | The period window used to get the orders data for. <i class="label label-info">read-only</i>         |
| `data`    | object | The orders data. It contains `value` and `products` data. <i class="label label-info">read-only</i>  |

#### Available parameters ####

| Parameter  | Type   | Description                                                                                                                    |
|------------|--------|--------------------------------------------------------------------------------------------------------------------------------|
| `period`   | string | The period to get orders data from. Default is `this_month`. Options: `this_month`, `previous_month`, `this_week` and `today`. |

## Retrieve promo sales widget data ##

This API lets you retrieve and view the Dashboard's promo sales widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/promo-sales</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/promo-sales?period=previous_month \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/promo-sales", {
  period: "previous_month"
})
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
$query = [
    'period' => 'previous_month'
];

print_r($woocommerce->get('atum/dashboard/promo-sales', $query));
?>
```

```python
print(wcapi.get("atum/dashboard/promo-sales?period=previous_month").json())
```

```ruby
query = {
  period: "previous_month"
}

woocommerce.get("atum/dashboard/promo-sales", query).parsed_response
```

> JSON response example:

```json
[
    {
        "period": "previous_month",
        "data": {
            "value": "&euro;2,00",
            "products": 1
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Promo sales widget properties ####

| Attribute | Type   | Description                                                                                               |
|-----------|--------|-----------------------------------------------------------------------------------------------------------|
| `period`  | string | The period window used to get the promo sales data for. <i class="label label-info">read-only</i>         |
| `data`    | object | The promo sales data. It contains `value` and `products` data. <i class="label label-info">read-only</i>  |

#### Available parameters ####

| Parameter  | Type   | Description                                                                                                                         |
|------------|--------|-------------------------------------------------------------------------------------------------------------------------------------|
| `period`   | string | The period to get promo sales data from. Default is `this_month`. Options: `this_month`, `previous_month`, `this_week` and `today`. |

## Retrieve stock control widget data ##

This API lets you retrieve and view the Dashboard's stock control widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/stock-control</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/stock-control \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/stock-control")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
print_r($woocommerce->get('atum/dashboard/stock-control'));
?>
```

```python
print(wcapi.get("atum/dashboard/stock-control").json())
```

```ruby
woocommerce.get("atum/dashboard/stock-control").parsed_response
```

> JSON response example:

```json
[
    {
        "stock_counters": {
            "count_in_stock": 34,
            "count_out_stock": 15,
            "count_low_stock": 0,
            "count_all": 68,
            "count_unmanaged": 4
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Stock control widget properties ####

| Attribute        | Type   | Description                                                                                                                                                               |
|------------------|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `stock_conuters` | object | The stock control data. It contains: `count_in_stock`, `count_out_stock`, `count_low_stock`, `count_all` and `count_unmanaged`. <i class="label label-info">read-only</i> |

## Retrieve current stock value widget data ##

This API lets you retrieve and view the Dashboard's current stock value widget data.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/dashboard/current-stock-value</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/dashboard/current-stock-value \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/dashboard/current-stock-value")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
print_r($woocommerce->get('atum/dashboard/current-stock-value'));
?>
```

```python
print(wcapi.get("atum/dashboard/current-stock-value").json())
```

```ruby
woocommerce.get("atum/dashboard/current-stock-value").parsed_response
```

> JSON response example:

```json
[
    {
        "current_stock_values": {
            "items_stocks_counter": 31867,
            "items_purchase_price_total": 59925.53,
            "items_without_purchase_price": 7410
        },
        "_links": {
            "about": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/dashboard"
                }
            ]
        }
    }
]
```

#### Current stock value widget properties ####

| Attribute | Type       | Description                                                                                                                                                                            |
|-----------|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `current_stock_values` | object | The current stock value data. It contains: `items_stock_counter`, `items_purchase_price_total`, and `items_without_purchase_price`. <i class="label label-info">read-only</i> |
