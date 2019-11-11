# Add-ons <i class="label label-atum">ATUM</i> #

The add-ons API allows you to view the installed ATUM add-ons and their licenses.

## Product properties ##

| Attribute | Type   | Description                                                                                                                                                                                                             |
|-----------|--------|-------------------------------------------------------------------------------------|
| `name`    | string | The add-on name. <i class="label label-info">read-only</i>                          |
| `key`     | string | The license key for the purchased add-on. <i class="label label-info">read-only</i> |
| `status`  | string | The license key status. <i class="label label-info">read-only</i>                   |

## List all add-ons ##

This API helps you to view all the add-ons.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/addons</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/addons \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/addons")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/addons')); ?>
```

```python
print(wcapi.get("atum/addons").json())
```

```ruby
woocommerce.get("atum/addons").parsed_response
```

> JSON response example:

```json
[
    {
        "name": "Product Levels",
        "key": "XXXXXX",
        "status": "valid"
    },
    {
        "name": "Stock Takes",
        "key": "",
        "status": "invalid"
    },
    {
        "name": "Stock Logs",
        "key": "",
        "status": "invalid"
    },
    {
        "name": "Dashboard Statistics Pro",
        "key": "",
        "status": "invalid"
    },
    {
        "name": "User Restrictions",
        "key": "",
        "status": "invalid"
    },
    {
        "name": "Data Export",
        "key": "",
        "status": "invalid"
    },
    {
        "name": "Multi-Inventory",
        "key": "XXXXXX",
        "status": "valid"
    },
    {
        "name": "Export Pro",
        "key": "",
        "status": "invalid"
    }
]
```

#### Available parameters ####

| Parameter | Type    | Description                                                   |
|-----------|---------|---------------------------------------------------------------|
| `name`    | string  | Filter the results to only those matching the specified name. |
