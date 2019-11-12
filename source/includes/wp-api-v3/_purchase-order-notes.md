# <i class="label label-atum">ATUM</i> Purchase order notes #

The purchase order notes API allows you to create, view, and delete individual purchase order notes.  
Purchase order notes are added by administrators and programmatically to store data about a purchase order, or its events.

## Purchase order note properties ##

| Attribute          | Type      | Description                                                                                                                         |
|--------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------|
| `id`               | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                       |
| `author`           | string    | Purchase order note author. <i class="label label-info">read-only</i>                                                               |
| `date_created`     | date-time | The date the purchase order note was created, in the site's timezone. <i class="label label-info">read-only</i>                     |
| `date_created_gmt` | date-time | The date the purchase order note was created, as GMT. <i class="label label-info">read-only</i>                                     |
| `note`             | string    | Purchase order note content. <i class="label label-info">mandatory</i>                                                              |
| `added_by_user`    | boolean   | If true, this note will be attributed to the current user. If false, the note will be attributed to the system. Default is `false`. |

## Create a purchase order note ##

This API helps you to create a new note for a purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;/notes</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/purchase-orders/713/notes \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "note": "FROM REST ok!!!"
}'
```

```javascript
const data = {
  note: "FROM REST ok!!!"
};

WooCommerce.post("atum/purchase-orders/852/notes", data)
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
    'note' => 'FROM REST ok!!!'
];

print_r($woocommerce->post('atum/purchase-orders/852/notes', $data));
?>
```

```python
data = {
    "note": "FROM REST ok!!!"
}

print(wcapi.post("atum/purchase-orders/852/notes", data).json())
```

```ruby
data = {
  note: "FROM REST ok!!!"
}

woocommerce.post("atum/purchase-orders/852/notes", data).parsed_response
```

> JSON response example:

```json
{
    "id": 4226,
    "author": "John Doe",
    "date_created": "2019-11-12T10:40:51",
    "date_created_gmt": "2019-11-12T09:40:51",
    "note": "FROM REST ok!!!",
    "added_by_user": true,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
            }
        ]
    }
}
```

## Retrieve a purchase order note ##

This API lets you retrieve and view a specific note from a purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;/notes/&lt;note_id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/purchase-orders/852/notes/4226")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/purchase-orders/852/notes/4226')); ?>
```

```python
print(wcapi.get("atum/purchase-orders/852/notes/4226").json())
```

```ruby
woocommerce.get("atum/purchase-orders/852/notes/4226").parsed_response
```

> JSON response example:

```json
{
    "id": 4226,
    "author": "John Doe",
    "date_created": "2019-11-12T10:40:51",
    "date_created_gmt": "2019-11-12T09:40:51",
    "note": "FROM REST ok!!!",
    "added_by_user": true,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
            }
        ]
    }
}
```

## List all purchase order notes ##

This API helps you to view all the notes from a purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;/notes</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/purchase-orders/852/notes")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/purchase-orders/852/notes')); ?>
```

```python
print(wcapi.get("atum/purchase-orders/852/notes").json())
```

```ruby
woocommerce.get("atum/purchase-orders/852/notes").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 4226,
        "author": "John Doe",
        "date_created": "2019-11-12T10:40:51",
        "date_created_gmt": "2019-11-12T09:40:51",
        "note": "FROM REST ok!!!",
        "added_by_user": true,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ]
        }
    },
    {
        "id": 3770,
        "author": "ATUM",
        "date_created": "2019-10-03T12:01:16",
        "date_created_gmt": "2019-10-03T10:01:16",
        "note": "Order status changed from Receiving to Received.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/3770"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ]
        }
    },
    {
        "id": 3752,
        "author": "ATUM",
        "date_created": "2019-10-02T13:36:44",
        "date_created_gmt": "2019-10-02T11:36:44",
        "note": "Order status changed from Pending to Receiving.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/3752"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ]
        }
    },    
    {
        "id": 1027,
        "author": "ATUM",
        "date_created": "2019-04-30T18:59:56",
        "date_created_gmt": "2019-04-30T16:59:56",
        "note": "Item 642 stock decreased from 23 to 22.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/1027"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ]
        }
    },
    {
        "id": 1028,
        "author": "ATUM",
        "date_created": "2019-04-30T18:59:56",
        "date_created_gmt": "2019-04-30T16:59:56",
        "note": "Order status changed from Received to Pending.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/1028"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ]
        }
    },
    {
        "id": 1025,
        "author": "ATUM",
        "date_created": "2019-04-30T18:56:54",
        "date_created_gmt": "2019-04-30T16:56:54",
        "note": "Item 642 stock increased from 22 to 23.",
        "added_by_user": false,
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/1025"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
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

## Delete a purchase order note ##

This API helps you delete a purchase order note.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;/notes/&lt;note_id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("atum/purchase-orders/852/notes/4226", {
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
<?php print_r($woocommerce->delete('atum/purchase-orders/852/notes/4226', ['force' => true])); ?>
```

```python
print(wcapi.delete("atum/purchase-orders/852/notes/4226", params={"force": True}).json())
```

```ruby
woocommerce.delete("atum/purchase-orders/852/notes/4226", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 4226,
    "author": "John Doe",
    "date_created": "2019-11-12T10:40:51",
    "date_created_gmt": "2019-11-12T09:40:51",
    "note": "FROM REST ok!!!",
    "added_by_user": true,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes/4226"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852/notes"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
            }
        ]
    }
}
```
#### Available parameters ####

| Parameter | Type   | Description                                                   |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |
