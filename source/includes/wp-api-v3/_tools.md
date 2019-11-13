# Tools #

The ATUM tools API allows you to view and run tools.

## Tool properties ##

| Attribute     | Type    | Description                                                                                                         |
| ------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `id`          | string  | A unique identifier for the tool. <i class="label label-info">read-only</i>                                         |
| `name`        | string  | Tool nice name. <i class="label label-info">read-only</i>                                                           |
| `description` | string  | Tool description. <i class="label label-info">read-only</i>                                                         |
| `config`      | object  | If the tool needs config in order to work.                                                                          |
| `success`     | boolean | Did the tool run successfully? <i class="label label-info">read-only</i> <i class="label label-info">write-only</i> |
| `message`     | string  | Tool return message. <i class="label label-info">read-only</i> <i class="label label-info">write-only</i>           |

## Retrieve a tool ##

This API lets you retrieve and view a specific tool by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/tools/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/tools/enable-atum-control \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/tools/enable-atum-control")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/tools/enable-atum-control')); ?>
```

```python
print(wcapi.get("atum/tools/enable-atum-control").json())
```

```ruby
woocommerce.get("atum/tools/enable-atum-control").parsed_response
```

> JSON response example:

```json
{
    "id": "enable-atum-control",
    "name": "Enable ATUM Stock Control",
    "description": "Enable the ATUM's stock control option for all the products at once.",
    "_links": {
        "item": [
            {
                "embeddable": true,
                "href": "https://example.com/wp-json/wc/v3/atum/tools/enable-atum-control"
            }
        ]
    }
}
```

## List all tools ##

This API helps you to view all the available ATUM tools.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/tools</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/tools \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/tools")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/tools')); ?>
```

```python
print(wcapi.get("atum/tools").json())
```

```ruby
woocommerce.get("atum/tools").parsed_response
```

> JSON response example:

```json
[
    {
        "id": "enable-manage-stock",
        "name": "Enable WC's Manage Stock",
        "description": "Enable the WooCommerce's manage stock at product level for all the products at once.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/enable-manage-stock"
                }
            ]
        }
    },
    {
        "id": "disable-manage-stock",
        "name": "Disable WC's Manage Stock",
        "description": "Disable the WooCommerce's manage stock at product level for all the products at once.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/disable-manage-stock"
                }
            ]
        }
    },
    {
        "id": "enable-atum-control",
        "name": "Enable ATUM Stock Control",
        "description": "Enable the ATUM's stock control option for all the products at once.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/enable-atum-control"
                }
            ]
        }
    },
    {
        "id": "disable-atum-control",
        "name": "Disable ATUM Stock Control",
        "description": "Disable the ATUM's stock control option for all the products at once.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/disable-atum-control"
                }
            ]
        }
    },
    {
        "id": "clear-out-stock-threshold",
        "name": "Clear Out of Stock Threshold",
        "description": "Clear all previously saved Out of Stock Threshold values.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/clear-out-stock-threshold"
                }
            ]
        }
    },
    {
        "id": "sync_calculated_stock",
        "name": "Sync WooCommerce stock with calculated stock",
        "description": "Sync all the associated BOM products' stock with their current calculated stock.",
        "_links": {
            "item": [
                {
                    "embeddable": true,
                    "href": "https://example.com/wp-json/wc/v3/atum/tools/sync_calculated_stock"
                }
            ]
        }
    }
]
```

## Run a tool ##

This API lets you run an ATUM tool.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/atum/tools/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/atum/tools/enable-manage-stock \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json"
```

```javascript
WooCommerce.put("atum/tools/enable-manage-stock")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php
print_r($woocommerce->put('atum/tools/enable-manage-stock'));
?>
```

```python
print(wcapi.put("atum/tools/enable-manage-stock").json())
```

```ruby
woocommerce.put("atum/tools/enable-manage-stock").parsed_response
```

> JSON response example:

```json
{
    "id": "enable-manage-stock",
    "name": "Enable WC's Manage Stock",
    "description": "Enable the WooCommerce's manage stock at product level for all the products at once.",
    "success": true,
    "message": "All your products were updated successfully",
    "_links": {
        "item": [
            {
                "embeddable": true,
                "href": "https://example.com/wp-json/wc/v3/atum/tools/enable-manage-stock"
            }
        ]
    }
}
```
