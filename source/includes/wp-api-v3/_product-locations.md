# Product locations <i class="label label-atum">ATUM</i> #

The ATUM product locations API allows you to create, view, update, and delete individual, or a batch, of locations.

## Product location properties ##

| Attribute     | Type    | Description                                                                                                      |
|---------------|---------|------------------------------------------------------------------------------------------------------------------|
| `id`          | integer | Unique identifier for the resource. <i class="label label-info">read-only</i>                                    |
| `name`        | string  | Location name. <i class="label label-info">mandatory</i>                                                         |
| `slug`        | string  | An alphanumeric identifier for the resource unique to its type.                                                  |
| `parent`      | integer | The ID for the parent of the resource.                                                                           |
| `description` | string  | HTML description of the resource.                                                                                |
| `count`       | integer | Number of published products for the resource. <i class="label label-info">read-only</i>                         |                                                                             |

## Create a product location ##

This API helps you to create a new product location.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/atum-locations</h6>
	</div>
</div>

> Example of how to create a product location:

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/atum-locations \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "name": "Manchester",
  "parent": 38
}'
```

```javascript
const data = {
   name: "Manchester",
   parent: 38
 };

WooCommerce.post("products/atum-locations", data)
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
  'name' => 'Manchester',
  'parent' => 38
];

print_r($woocommerce->post('products/atum-locations', $data));
?>
```

```python
data = {
    "name": "Manchester",
    "parent": 38
}

print(wcapi.post("products/atum-locations", data).json())
```

```ruby
data = {
  name: "Manchester",
  parent: 38
}

woocommerce.post("products/atum-locations", data).parsed_response
```

> JSON response example:

```json
{
    "id": 58,
    "name": "Manchester",
    "slug": "manchester",
    "parent": 38,
    "description": "",
    "count": 0,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/58"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
            }
        ]
    }
}
```

## Retrieve a product location ##

This API lets you retrieve a product location by ID.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/atum-locations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/atum-locations/38 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/atum-locations/38")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/atum-locations/38')); ?>
```

```python
print(wcapi.get("products/atum-locations/38").json())
```

```ruby
woocommerce.get("products/atum-locations/38").parsed_response
```

> JSON response example:

```json
{
    "id": 38,
    "name": "United Kingdom",
    "slug": "united-kingdom",
    "parent": 0,
    "description": "",
    "count": 7,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
            }
        ]
    }
}
```

## List all product locations ##

This API lets you retrieve all product locations.

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/atum-locations</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/atum-locations \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/atum-locations")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/atum-locations')); ?>
```

```python
print(wcapi.get("products/atum-locations").json())
```

```ruby
woocommerce.get("products/atum-locations").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 39,
        "name": "Italy",
        "slug": "italy",
        "parent": 0,
        "description": "",
        "count": 5,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/39"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ]
        }
    },
    {
        "id": 50,
        "name": "Madrid",
        "slug": "madrid",
        "parent": 37,
        "description": "",
        "count": 3,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/50"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/37"
                }
            ]
        }
    },
    {
        "id": 58,
        "name": "Manchester",
        "slug": "manchester",
        "parent": 38,
        "description": "",
        "count": 0,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/58"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
                }
            ]
        }
    },
    {
        "id": 53,
        "name": "Slovakia",
        "slug": "slovakia",
        "parent": 0,
        "description": "",
        "count": 0,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/53"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ]
        }
    },
    {
        "id": 37,
        "name": "Spain",
        "slug": "spain",
        "parent": 0,
        "description": "",
        "count": 7,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/37"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ]
        }
    },
    {
        "id": 38,
        "name": "United Kingdom",
        "slug": "united-kingdom",
        "parent": 0,
        "description": "",
        "count": 7,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ]
        }
    },
    {
        "id": 49,
        "name": "Valencia",
        "slug": "valencia",
        "parent": 37,
        "description": "",
        "count": 6,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/49"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/atum-locations/37"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter    | Type    | Description                                                                                                                                  |
|--------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------|
| `context`    | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                 |
| `page`       | integer | Current page of the collection. Default is `1`.                                                                                              |
| `per_page`   | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                       |
| `search`     | string  | Limit results to those matching a string.                                                                                                    |
| `exclude`    | array   | Ensure result set excludes specific ids.                                                                                                     |
| `include`    | array   | Limit result set to specific ids.                                                                                                            |
| `order`      | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `asc`.                                                   |
| `orderby`    | string  | Sort collection by resource attribute. Options: `id`, `include`, `name`, `slug`, `term_group`, `description` and `count`. Default is `name`. |
| `hide_empty` | boolean | Whether to hide resources not assigned to any products. Default is `false`.                                                                  |
| `parent`     | integer | Limit result set to resources assigned to a specific parent.                                                                                 |
| `product`    | integer | Limit result set to resources assigned to a specific product.                                                                                |
| `slug`       | string  | Limit result set to resources with a specific slug.                                                                                          |

## Update a product location ##

This API lets you make changes to a product location.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/products/atum-locations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/products/atum-locations/58 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "description": "Manchester city."
}'
```

```javascript
const data = {
  description: "Manchester city."
};

WooCommerce.put("products/atum-locations/58", data)
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
    'description' => 'Manchester city.'
];

print_r($woocommerce->put('products/atum-locations/58', $data));
?>
```

```python
data = {
    "description": "Manchester city."
}

print(wcapi.put("products/atum-locations/58", data).json())
```

```ruby
data = {
  description: "Manchester city."
}

woocommerce.put("products/atum-locations/58", data).parsed_response
```

> JSON response example:

```json
{
    "id": 58,
    "name": "Manchester",
    "slug": "manchester",
    "parent": 38,
    "description": "Manchester city.",
    "count": 0,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/58"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
            }
        ]
    }
}
```

## Delete a product location ##

This API helps you delete a product location.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/products/atum-locations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/products/atum-locations/58?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("products/atum-locations/58", {
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
<?php print_r($woocommerce->delete('products/atum-locations/58', ['force' => true])); ?>
```

```python
print(wcapi.delete("products/atum-locations/58", params={"force": True}).json())
```

```ruby
woocommerce.delete("products/atum-locations/58", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 58,
    "name": "Manchester",
    "slug": "manchester",
    "parent": 38,
    "description": "Manchester city.",
    "count": 0,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/58"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                   |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |

## Batch update product locations ##

This API helps you to batch create, update and delete multiple product locations.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/atum-locations/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com//wp-json/wc/v3/products/atum-locations/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
    "create": [
        {
          "name": "London",
          "parent": 38
        },
        {
          "name": "Portugal"
        }
    ],
    "update": [
        {
            "id": 49,
            "description": "Valencia city."
        }	
    ],
    "delete": [
        59	
    ]
}'
```

```javascript
const data = {
    create: [
        {
          name: "London",
          parent: 38
        },
        {
          name: "Portugal"
        }
    ],
    update: [
        {
            id: 49,
            description: "Valencia city."
        }	
    ],
    delete: [
        59	
    ]
};

WooCommerce.post("products/atum-locations/batch", data)
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
          'name' => 'London',
          'parent' => 38
        ],
        [
          'name' => 'Portugal'
        ]
    ],
    'update' => [
        [
            'id' => 49,
            'description' => 'Valencia city.'
        ]	
    ],
    'delete' => [
        59	
    ]
];

print_r($woocommerce->post('products/atum-locations/batch', $data));
?>
```

```python
data = {
    "create": [
        {
          "name": "London",
          "parent": 38
        },
        {
          "name": "Portugal"
        }
    ],
    "update": [
        {
            "id": 49,
            "description": "Valencia city."
        }	
    ],
    "delete": [
        59	
    ]
}

print(wcapi.post("products/atum-locations/batch", data).json())
```

```ruby
data = {
    create: [
        {
          name: "London",
          parent: 38
        },
        {
          name: "Portugal"
        }
    ],
    update: [
        {
            id: 49,
            description: "Valencia city."
        }	
    ],
    delete: [
        59	
    ]
}

woocommerce.post("products/atum-locations/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 60,
            "name": "London",
            "slug": "london",
            "parent": 38,
            "description": "",
            "count": 0,
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/60"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
                    }
                ]
            }
        },
        {
            "id": 61,
            "name": "Portugal",
            "slug": "portugal",
            "parent": 0,
            "description": "",
            "count": 0,
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/61"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 49,
            "name": "Valencia",
            "slug": "valencia",
            "parent": 37,
            "description": "Valencia city.",
            "count": 6,
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/49"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/37"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 59,
            "name": "Manchester",
            "slug": "manchester",
            "parent": 38,
            "description": "",
            "count": 0,
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/59"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/atum-locations/38"
                    }
                ]
            }
        }
    ]
}
```
