# Settings #

The settings API allows you to view all groups of ATUM settings available.

## Setting group properties ##

| Attribute     | Type   | Description                                                                                                |
|---------------|--------|------------------------------------------------------------------------------------------------------------|
| `id`          | string | A unique identifier that can be used to link settings together. <i class="label label-info">read-only</i>  |
| `label`       | string | A human readable label for the setting used in interfaces. <i class="label label-info">read-only</i>       |
| `description` | string | A human readable description for the setting used in interfaces. <i class="label label-info">read-only</i> |
| `sections`    | string | IDs for settings sections within groups. <i class="label label-info">read-only</i>                                     |

## List all settings groups ##

This API helps you to view all the settings groups.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/settings</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/settings \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/settings")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/settings')); ?>
```

```python
print(wcapi.get("atum/settings").json())
```

```ruby
woocommerce.get("atum/settings").parsed_response
```

> JSON response example:

```json
[
    {
        "id": "general",
        "label": "General",
        "description": "",
        "sections": {
            "general": "General Options"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "store_details",
        "label": "Store Details",
        "description": "",
        "sections": {
            "company": "Company info",
            "shipping": "Shipping info"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/store_details"
                }
            ]
        }
    },
    {
        "id": "module_manager",
        "label": "Modules",
        "description": "",
        "sections": {
            "module_manager": "Module Manager"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/module_manager"
                }
            ]
        }
    },
    {
        "id": "visual_settings",
        "label": "Visual Settings",
        "description": "",
        "sections": {
            "color_mode": "Color Mode",
            "color_scheme": "Color Scheme"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/visual_settings"
                }
            ]
        }
    },
    {
        "id": "multi_inventory",
        "label": "Multi-Inventory",
        "description": "",
        "sections": {
            "multi_inventory": "Multi-Inventory Options",
            "geoprompt": "Geo Prompt Popup"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/multi_inventory"
                }
            ]
        }
    },
    {
        "id": "product_levels",
        "label": "Product Levels",
        "description": "",
        "sections": {
            "product_levels": "General Options",
            "manufacturing_central": "Manufacturing Central Options"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/product_levels"
                }
            ]
        }
    },
    {
        "id": "tools",
        "label": "Tools",
        "description": "",
        "sections": {
            "tools": "ATUM Tools"
        },
        "_links": {
            "options": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/tools"
                }
            ]
        }
    }
]
```
