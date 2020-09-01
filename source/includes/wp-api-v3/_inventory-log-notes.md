# Inventory log notes #

<i class="label label-atum">ATUM</i>

The inventory log notes API allows you to create, view, and delete individual inventory log notes.  
Inventory log notes are added by administrators and programmatically to store data about an inventory log, or its events.

## Inventory log note properties ##

| Attribute          | Type      | Description                                                                                                                         |
|--------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| `id`               | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                       |
| `author`           | string    | Inventory log note author. <i class="label label-info">read-only</i>                                                                        |
| `date_created`     | date-time | The date the inventory log note was created, in the site's timezone. <i class="label label-info">read-only</i>                              |
| `date_created_gmt` | date-time | The date the inventory log note was created, as GMT. <i class="label label-info">read-only</i>                                              |
| `note`             | string    | Inventory log note content. <i class="label label-info">mandatory</i>                                                                       |
| `added_by_user`    | boolean   | If true, this note will be attributed to the current user. If false, the note will be attributed to the system. Default is `false`. |

## Create an inventory log note ##

This API helps you to create a new note for an inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;/notes</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "note": "Test Note!!!"
}'
```

```javascript
const data = {
  note: "Test Note!!!"
};

WooCommerce.post("atum/inventory-logs/713/notes", data)
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
    'note' => 'Test Note!!!'
];

print_r($woocommerce->post('atum/inventory-logs/713/notes', $data));
?>
```

```python
data = {
    "note": "Test Note!!!"
}

print(wcapi.post("atum/inventory-logs/713/notes", data).json())
```

```ruby
data = {
  note: "Test Note!!!"
}

woocommerce.post("atum/inventory-logs/713/notes", data).parsed_response
```

> JSON response example:

```json
{
    "id": 4202,
    "author": "John Doe",
    "date_created": "2019-11-11T13:27:10",
    "date_created_gmt": "2019-11-11T12:27:10",
    "note": "Test Note!!!",
    "added_by_user": false,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes/4202"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
            }
        ]
    }
}
```

## Retrieve an inventory log note ##

This API lets you retrieve and view a specific note from an inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;/notes/&lt;note_id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes/4202 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inventory-logs/713/notes/4202")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inventory-logs/713/notes/4202')); ?>
```

```python
print(wcapi.get("atum/inventory-logs/713/notes/4202").json())
```

```ruby
woocommerce.get("atum/inventory-logs/713/notes/4202").parsed_response
```

> JSON response example:

```json
{
    "id": 4202,
    "author": "John Doe",
    "date_created": "2019-11-11T13:27:10",
    "date_created_gmt": "2019-11-11T12:27:10",
    "note": "Test Note!!!",
    "added_by_user": false,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes/4202"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
            }
        ]
    }
}
```

## List all inventory log notes ##

This API helps you to view all the notes from an inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;/notes</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inventory-logs/493/notes")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inventory-logs/493/notes')); ?>
```

```python
print(wcapi.get("atum/inventory-logs/493/notes").json())
```

```ruby
woocommerce.get("atum/inventory-logs/493/notes").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 616,
        "author": "John Doe",
        "date_created": "2019-03-12T09:47:46",
        "date_created_gmt": "2019-03-12T09:47:46",
        "note": "testing",
        "added_by_user": true,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/616"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 589,
        "author": "ATUM",
        "date_created": "2019-03-05T11:17:16",
        "date_created_gmt": "2019-03-05T11:17:16",
        "note": "Order status changed from Completed to Pending.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/589"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 588,
        "author": "ATUM",
        "date_created": "2019-03-05T11:16:26",
        "date_created_gmt": "2019-03-05T11:16:26",
        "note": "Order status changed from Pending to Completed.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/588"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 274,
        "author": "ATUM",
        "date_created": "2018-04-04T07:26:35",
        "date_created_gmt": "2018-04-04T06:26:35",
        "note": "Item 24 stock increased from 4 to 5.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/274"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 266,
        "author": "ATUM",
        "date_created": "2018-03-14T11:32:20",
        "date_created_gmt": "2018-03-14T11:32:20",
        "note": "Item 24 stock increased from 3 to 4.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/266"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 255,
        "author": "ATUM",
        "date_created": "2018-03-06T08:04:30",
        "date_created_gmt": "2018-03-06T08:04:30",
        "note": "Item 24 stock decreased from 2 to 1.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/255"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    },
    {
        "id": 254,
        "author": "ATUM",
        "date_created": "2018-03-06T08:04:12",
        "date_created_gmt": "2018-03-06T08:04:12",
        "note": "Item 24 stock increased from 1 to 2.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes/254"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter | Type   | Description                                                                                  |
|-----------|--------|----------------------------------------------------------------------------------------------|
| `type`    | string | Limit result to user or system notes. Options: `any`, `user` and `system`. Default is `any`. |

## Delete an inventory log note ##

This API helps you delete an inventory log note.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;/notes/&lt;note_id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes/4202?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("atum/inventory-logs/713/notes/4202", {
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
<?php print_r($woocommerce->delete('atum/inventory-logs/713/notes/4202', ['force' => true])); ?>
```

```python
print(wcapi.delete("atum/inventory-logs/713/notes/4202", params={"force": True}).json())
```

```ruby
woocommerce.delete("atum/inventory-logs/713/notes/4202", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 4202,
    "author": "ATUM",
    "date_created": "2019-11-11T13:27:10",
    "date_created_gmt": "2019-11-11T12:27:10",
    "note": "Test Note!!!",
    "added_by_user": false,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes/4202"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
            }
        ]
    }
}
```
#### Available parameters ####

| Parameter | Type   | Description                                                   |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |
