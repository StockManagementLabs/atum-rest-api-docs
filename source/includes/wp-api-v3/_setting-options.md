# <i class="label label-atum">ATUM</i> Setting options #

## Setting option properties ##

| Attribute     | Type   | Description                                                                                                                                                                                                  |
|---------------|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`          | string | A unique identifier for the setting. <i class="label label-info">read-only</i>                                                                                                                               |
| `group_id`    | string | An identifier for the group this setting belongs to. <i class="label label-info">read-only</i>                                                                                                               |
| `section`     | string | An identifier for the group section this setting belongs to. <i class="label label-info">read-only</i>                                                                                                       |
| `name`        | string | A human readable name for the setting used in interfaces. <i class="label label-info">read-only</i>                                                                                                          |
| `desc`        | string | A human readable description for the setting used in interfaces. <i class="label label-info">read-only</i>                                                                                                   |
| `value`       | mixed  | Setting value.                                                                                                                                                                                               |
| `default`     | mixed  | Default value for the setting. <i class="label label-info">read-only</i>                                                                                                                                     |
| `type`        | string | Type of setting. Options: `text`, `number`, `color`, `switcher`, `textarea`, `select`, `html`, `wc_country`, `button_group`, `script_runner` and `theme_selector`. <i class="label label-info">read-only</i> |
| `options`     | object | Array of options (key value pairs) for inputs such as select, multiselect, and radio buttons. <i class="label label-info">read-only</i>                                                                      |
| `dependency`  | object | The dependency config array for any depedent settings. <i class="label label-info">read-only</i>                                                                                                             |
| `confirm_msg` | string | The message that is shown when a confirmation is needed when changing a setting. <i class="label label-info">read-only</i>                                                                                   |

## Retrieve a setting option ##

This API lets you retrieve and view a specific setting option.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/settings/&lt;group_id&gt;/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/settings/general/show_totals \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/settings/general/show_totals")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/settings/general/show_totals')); ?>
```

```python
print(wcapi.get("atum/settings/general/show_totals").json())
```

```ruby
woocommerce.get("atum/settings/general/show_totals").parsed_response
```

> JSON response example:

```json
{
    "id": "show_totals",
    "group": "general",
    "section": "general",
    "name": "Show Totals Row",
    "desc": "When enabled, ATUM will display new row at the bottom of Stock Central. You will be able to preview page column totals of essential stock counters.",
    "type": "switcher",
    "default": "yes",
    "value": "yes",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/settings/general/show_totals"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
            }
        ]
    }
}
```

## List all setting options ##

This API helps you to view all the setting options.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/settings/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/settings/general \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/settings/general")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/settings/general')); ?>
```

```python
print(wcapi.get("atum/settings/general").json())
```

```ruby
woocommerce.get("atum/settings/general").parsed_response
```

> JSON response example:

```json
[
    {
        "id": "enable_ajax_filter",
        "group": "general",
        "section": "general",
        "name": "Enable Filter Autosearch",
        "desc": "When enabled, the manual search button disappears. Disable this function if you don't use or find the automatic search feature helpful.",
        "type": "switcher",
        "default": "yes",
        "value": "no",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/enable_ajax_filter"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "enhanced_suppliers_filter",
        "group": "general",
        "section": "general",
        "name": "Enhanced Suppliers' Filter",
        "desc": "When enabled, the List Tables Suppliers' filter will be replaced by an advanced search box. Recommended for sites with many suppliers.",
        "type": "switcher",
        "default": "no",
        "value": "yes",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/enhanced_suppliers_filter"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "show_totals",
        "group": "general",
        "section": "general",
        "name": "Show Totals Row",
        "desc": "When enabled, ATUM will display new row at the bottom of Stock Central. You will be able to preview page column totals of essential stock counters.",
        "type": "switcher",
        "default": "yes",
        "value": "yes",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/show_totals"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "enable_admin_bar_menu",
        "group": "general",
        "section": "general",
        "name": "Enable Admin Bar Menu",
        "desc": "When enabled, the ATUM menu will be accessible through the WP admin bar.",
        "type": "switcher",
        "default": "yes",
        "value": "yes",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/enable_admin_bar_menu"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "show_variations_stock",
        "group": "general",
        "section": "general",
        "name": "Override 'Out of stock' Status",
        "desc": "When enabled, the variations' stock status will be displayed in WooCommerce products' list for variable products. This overrides the 'Out of stock' status displayed by WooCommerce, when stock is managed at product level for variable products.",
        "type": "switcher",
        "default": "yes",
        "value": "yes",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/show_variations_stock"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "out_stock_threshold",
        "group": "general",
        "section": "general",
        "name": "Out of Stock Threshold per product",
        "desc": "Activate the switch to disable WooCommerce's global out of stock threshold setting and enable ATUM's out of stock threshold per product. All products will inherit the WooCommerce's global value by default (if set).<br><br>\n\t\t\t                          Deactivate the switch to disable ATUM's out of stock threshold per product and re-enable the WooCommerce's global out of stock threshold. All your saved individual values will remain untouched in your database and ready for a future use, in case you decide to return to the individual control.<br><br>\n\t\t\t\t                      We have a specific tool to clear all the individual out of stock threshold values in the 'Tools' section.",
        "type": "switcher",
        "default": "no",
        "confirm_msg": "This will clear all the Out Stock Threshold values that have been set in all products",
        "value": "yes",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/out_stock_threshold"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "unmanaged_counters",
        "group": "general",
        "section": "general",
        "name": "Unmanaged Product Counters",
        "desc": "Add 'In Stock', 'Out of Stock' and 'Back Ordered' counters and views for Unmanaged by WooCommerce Products in all ATUM list tables. This option will also add these products to the Dashboard Stock Control Widget. Please note that enabling this option can affect the performance in stores with a large number of products.",
        "type": "switcher",
        "default": "no",
        "value": "no",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/unmanaged_counters"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "stock_quantity_decimals",
        "group": "general",
        "section": "general",
        "name": "Decimals in Stock Quantity",
        "desc": "Enter the number of decimal places your shop needs in stock quantity fields.  Set 0 to keep or 1 and higher to override the default WooCommerce NO decimal setting.",
        "type": "number",
        "default": 0,
        "options": {
            "min": 0,
            "max": 4
        },
        "value": 0,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/stock_quantity_decimals"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "stock_quantity_step",
        "group": "general",
        "section": "general",
        "name": "Stock change arrows behaviour",
        "desc": "Tell WooCommerce, how much to increase/decrease the stock value with each arrow click. Example: If set to ‘0.5’; the stock will change from value ‘5’ to value ‘5.5’ when pressing the UP arrow. Pressing the DOWN arrow will reduce the stock to ‘4.5’.",
        "type": "number",
        "default": 0,
        "options": {
            "min": 0,
            "max": 4,
            "step": 0.01
        },
        "value": 0,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/stock_quantity_step"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "sales_last_ndays",
        "group": "general",
        "section": "general",
        "name": "Show sales in the last selected days",
        "desc": "Enter the number of days to calculate the number of sales in that period in one Stock Central column.",
        "type": "number",
        "default": 14,
        "options": {
            "min": 1,
            "max": 31
        },
        "value": 14,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/sales_last_ndays"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    },
    {
        "id": "delete_data",
        "group": "general",
        "section": "general",
        "name": "Delete Data When Uninstalling",
        "desc": "Enable before uninstalling to remove all the data stored by ATUM in your database. Not recommended if you plan to reinstall ATUM in the future.",
        "type": "switcher",
        "default": "no",
        "value": "no",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general/delete_data"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                }
            ]
        }
    }
]
```

## Update a setting option ##

This API lets you make changes to a setting option.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/atum/settings/&lt;group_id&gt;/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/atum/settings/general/show_totals \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "value": "no"
}'
```

```javascript
const data = {
  value: "no"
};

WooCommerce.put("atum/settings/general/show_totals", data)
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
    'value' => 'no'
];

print_r($woocommerce->put('atum/settings/general/show_totals', $data));
?>
```

```python
data = {
    "value": "no"
}

print(wcapi.put("atum/settings/general/show_totals", data).json())
```

```ruby
data = {
  value: "no"
}

woocommerce.put("atum/settings/general/show_totals", data).parsed_response
```

> JSON response example:

```json
{
    "id": "show_totals",
    "group": "general",
    "section": "general",
    "name": "Show Totals Row",
    "desc": "When enabled, ATUM will display new row at the bottom of Stock Central. You will be able to preview page column totals of essential stock counters.",
    "type": "switcher",
    "default": "yes",
    "value": "no",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/settings/general/show_totals"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
            }
        ]
    }
}
```

## Batch update setting options ##

This API helps you to batch update multiple setting options.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/settings/&lt;id&gt;/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/settings/general/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "update": [
        {
          "id": "enable_ajax_filter",
          "value": "yes"
        },
        {
          "id": "enhanced_suppliers_filter",
          "value": "yes"
        },
        {
          "id": "show_totals",
          "value": "yes"
        }
      ]
    }'
```

```javascript
const data = {
   update: [
     {
       id: "enable_ajax_filter",
       value: "yes"
     },
     {
       id: "enhanced_suppliers_filter",
       value: "yes"
     },
     {
       id: "show_totals",
       value: "yes"
     }
   ]
};

WooCommerce.post("atum/settings/general/batch", data)
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
  'update' => [
    [
      'id' => 'enable_ajax_filter',
      'value' => 'yes'
    ],
    [
      'id' => 'enhanced_suppliers_filter',
      'value' => 'yes'
    ],
    [
      'id' => 'show_totals',
      'value' => 'yes'
    ]
  ]
];

print_r($woocommerce->post('atum/settings/general/batch', $data));
?>
```

```python
data = {
 "update": [
   {
     "id": "enable_ajax_filter",
     "value": "yes"
   },
   {
     "id": "enhanced_suppliers_filter",
     "value": "yes"
   },
   {
     "id": "show_totals",
     "value": "yes"
   }
 ]
}

print(wcapi.post("atum/settings/general/batch", data).json())
```

```ruby
data = {
 update: [
   {
     id: "enable_ajax_filter",
     value: "yes"
   },
   {
     id: "enhanced_suppliers_filter",
     value: "yes"
   },
   {
     id: "show_totals",
     value: "yes"
   }
 ]
}

woocommerce.post("atum/settings/general/batch", data).parsed_response
```

> JSON response example:

```json
{
    "update": [
        {
            "id": "enable_ajax_filter",
            "group": "general",
            "section": "general",
            "name": "Enable Filter Autosearch",
            "desc": "When enabled, the manual search button disappears. Disable this function if you don't use or find the automatic search feature helpful.",
            "type": "switcher",
            "default": "yes",
            "value": "yes",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general/enable_ajax_filter"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                    }
                ]
            }
        },
        {
            "id": "enhanced_suppliers_filter",
            "group": "general",
            "section": "general",
            "name": "Enhanced Suppliers' Filter",
            "desc": "When enabled, the List Tables Suppliers' filter will be replaced by an advanced search box. Recommended for sites with many suppliers.",
            "type": "switcher",
            "default": "no",
            "value": "yes",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general/enhanced_suppliers_filter"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                    }
                ]
            }
        },
        {
            "id": "show_totals",
            "group": "general",
            "section": "general",
            "name": "Show Totals Row",
            "desc": "When enabled, ATUM will display new row at the bottom of Stock Central. You will be able to preview page column totals of essential stock counters.",
            "type": "switcher",
            "default": "yes",
            "value": "yes",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general/show_totals"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/settings/general"
                    }
                ]
            }
        }
    ]
}
```
