# System status tools #

The system status tools API allows you to view and run tools from system status.

## System status tool properties ##

| Attribute     | Type    | Description                                                                                                         |
| ------------- | ------- | ------------------------------------------------------------------------------------------------------------------- |
| `id`          | string  | A unique identifier for the tool. <i class="label label-info">read-only</i>                                         |
| `name`        | string  | Tool name. <i class="label label-info">read-only</i>                                                                |
| `action`      | string  | What running the tool will do. <i class="label label-info">read-only</i>                                            |
| `description` | string  | Tool description. <i class="label label-info">read-only</i>                                                         |
| `success`     | boolean | Did the tool run successfully? <i class="label label-info">read-only</i> <i class="label label-info">write-only</i> |
| `message`     | string  | Tool return message. <i class="label label-info">read-only</i> <i class="label label-info">write-only</i>           |
| `confirm`     | boolean | Confirm execution of the tool. Default is `false`. <i class="label label-info">write-only</i>                       |

## Retrieve a tool from system status ##

This API lets you retrieve and view a specific tool from system status by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/system_status/tools/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/system_status/tools/clear_transients \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("system_status/tools/clear_transients")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('system_status/tools/clear_transients')); ?>
```

```python
print(wcapi.get("system_status/tools/clear_transients").json())
```

```ruby
woocommerce.get("system_status/tools/clear_transients").parsed_response
```

> JSON response example:

```json
{
  "id": "clear_transients",
  "name": "WC transients",
  "action": "Clear transients",
  "description": "This tool will clear the product/shop transients cache.",
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v3/system_status/tools/clear_transients"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v3/system_status/tools"
      }
    ]
  }
}
```

## List all tools from system status ##

This API helps you to view all tools from system status.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/system_status/tools</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/system_status/tools \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("system_status/tools")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('system_status/tools')); ?>
```

```python
print(wcapi.get("system_status/tools").json())
```

```ruby
woocommerce.get("system_status/tools").parsed_response
```

> JSON response example:

```json
[
  {
    "id": "clear_transients",
    "name": "WC transients",
    "action": "Clear transients",
    "description": "This tool will clear the product/shop transients cache.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/clear_transients"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "clear_expired_transients",
    "name": "Expired transients",
    "action": "Clear expired transients",
    "description": "This tool will clear ALL expired transients from WordPress.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/clear_expired_transients"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "delete_orphaned_variations",
    "name": "Orphaned variations",
    "action": "Delete orphaned variations",
    "description": "This tool will delete all variations which have no parent.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/delete_orphaned_variations"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "recount_terms",
    "name": "Term counts",
    "action": "Recount terms",
    "description": "This tool will recount product terms - useful when changing your settings in a way which hides products from the catalog.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/recount_terms"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "reset_roles",
    "name": "Capabilities",
    "action": "Reset capabilities",
    "description": "This tool will reset the admin, customer and shop_manager roles to default. Use this if your users cannot access all of the WooCommerce admin pages.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/reset_roles"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "clear_sessions",
    "name": "Customer sessions",
    "action": "Clear all sessions",
    "description": "<strong class=\"red\">Note:</strong> This tool will delete all customer session data from the database, including any current live carts.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/clear_sessions"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "install_pages",
    "name": "Install WooCommerce pages",
    "action": "Install pages",
    "description": "<strong class=\"red\">Note:</strong> This tool will install all the missing WooCommerce pages. Pages already defined and set up will not be replaced.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/install_pages"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "delete_taxes",
    "name": "Delete all WooCommerce tax rates",
    "action": "Delete ALL tax rates",
    "description": "<strong class=\"red\">Note:</strong> This option will delete ALL of your tax rates, use with caution.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/delete_taxes"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  },
  {
    "id": "reset_tracking",
    "name": "Reset usage tracking settings",
    "action": "Reset usage tracking settings",
    "description": "This will reset your usage tracking settings, causing it to show the opt-in banner again and not sending any data.",
    "_links": {
      "self": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools/reset_tracking"
        }
      ],
      "collection": [
        {
          "href": "https://example.com/wp-json/wc/v3/system_status/tools"
        }
      ]
    }
  }
]
```

## Run a tool from system status ##

This API lets you run a tool from system status.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/system_status/tools/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/system_status/tools/clear_transients \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "confirm": true
}'
```

```javascript
const data = {
  confirm: true
};

WooCommerce.put("system_status/tools/clear_transients", data)
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
    'confirm' => true
];

print_r($woocommerce->put('system_status/tools/clear_transients', $data));
?>
```

```python
data = {
    "confirm": True
}

print(wcapi.put("system_status/tools/clear_transients", data).json())
```

```ruby
data = {
  confirm: true
}

woocommerce.put("system_status/tools/clear_transients", data).parsed_response
```

> JSON response example:

```json
{
  "id": "clear_transients",
  "name": "WC transients",
  "action": "Clear transients",
  "description": "This tool will clear the product/shop transients cache.",
  "success": true,
  "message": "Product transients cleared",
  "_links": {
    "self": [
      {
        "href": "https://example.com/wp-json/wc/v3/system_status/tools/clear_transients"
      }
    ],
    "collection": [
      {
        "href": "https://example.com/wp-json/wc/v3/system_status/tools"
      }
    ]
  }
}
```
