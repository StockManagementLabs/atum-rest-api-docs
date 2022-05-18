# Product variations #

This endpoint is an extension of the official WC's orders enndpoint with extra info added by ATUM and/or its add-ons. 
You can identify the ATUM data with the corresponding labels.

The product variations API allows you to create, view, update, and delete individual, or a batch, of product variations.

## Product variation properties ##

| Attribute                | Type      | Description                                                                                                                                                                                                                                   |
|--------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                     | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                                                 |
| `date_created`           | date-time | The date the variation was created, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                         |
| `date_created_gmt`       | date-time | The date the variation was created, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                         |
| `date_modified`          | date-time | The date the variation was last modified, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                   |
| `date_modified_gmt`      | date-time | The date the variation was last modified, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                   |
| `description`            | string    | Variation description.                                                                                                                                                                                                                        |
| `permalink`              | string    | Variation URL. <i class="label label-info">read-only</i>                                                                                                                                                                                      |
| `sku`                    | string    | Unique identifier.                                                                                                                                                                                                                            |
| `price`                  | string    | Current variation price. <i class="label label-info">read-only</i>                                                                                                                                                                            |
| `regular_price`          | string    | Variation regular price.                                                                                                                                                                                                                      |
| `sale_price`             | string    | Variation sale price.                                                                                                                                                                                                                         |
| `date_on_sale_from`      | date-time | Start date of sale price, in the site's timezone.                                                                                                                                                                                             |
| `date_on_sale_from_gmt`  | date-time | Start date of sale price, as GMT.                                                                                                                                                                                                             |
| `date_on_sale_to`        | date-time | End date of sale price, in the site's timezone.                                                                                                                                                                                               |
| `date_on_sale_to_gmt`    | date-time | End date of sale price, as GMT.                                                                                                                                                                                                               |
| `on_sale`                | boolean   | Shows if the variation is on sale. <i class="label label-info">read-only</i>                                                                                                                                                                  |
| `status`                 | string    | Variation status. Options: `draft`, `pending`, `private` and `publish`. Default is `publish`.                                                                                                                                                 |
| `purchasable`            | boolean   | Shows if the variation can be bought. <i class="label label-info">read-only</i>                                                                                                                                                               |
| `virtual`                | boolean   | If the variation is virtual. Default is `false`.                                                                                                                                                                                              |
| `downloadable`           | boolean   | If the variation is downloadable. Default is `false`.                                                                                                                                                                                         |
| `downloads`              | array     | List of downloadable files. See [Product variation - Downloads properties](#product-variation-downloads-properties)                                                                                                                           |
| `download_limit`         | integer   | Number of times downloadable files can be downloaded after purchase. Default is `-1`.                                                                                                                                                         |
| `download_expiry`        | integer   | Number of days until access to downloadable files expires. Default is `-1`.                                                                                                                                                                   |
| `tax_status`             | string    | Tax status. Options: `taxable`, `shipping` and `none`. Default is `taxable`.                                                                                                                                                                  |
| `tax_class`              | string    | Tax class.                                                                                                                                                                                                                                    |
| `manage_stock`           | boolean   | Stock management at variation level. Default is `false`.                                                                                                                                                                                      |
| `stock_quantity`         | integer   | Stock quantity.                                                                                                                                                                                                                               |
| `stock_status`           | string    | Controls the stock status of the product. Options: `instock`, `outofstock`, `onbackorder`. Default is `instock`.                                                                                                                              |
| `backorders`             | string    | If managing stock, this controls if backorders are allowed. Options: `no`, `notify` and `yes`. Default is `no`.                                                                                                                               |
| `backorders_allowed`     | boolean   | Shows if backorders are allowed. <i class="label label-info">read-only</i>                                                                                                                                                                    |
| `backordered`            | boolean   | Shows if the variation is on backordered. <i class="label label-info">read-only</i>                                                                                                                                                           |
| `weight`                 | string    | Variation weight.                                                                                                                                                                                                                             |
| `dimensions`             | object    | Variation dimensions. See [Product variation - Dimensions properties](#product-variation-dimensions-properties)                                                                                                                               |
| `shipping_class`         | string    | Shipping class slug.                                                                                                                                                                                                                          |
| `shipping_class_id`      | string    | Shipping class ID. <i class="label label-info">read-only</i>                                                                                                                                                                                  |
| `image`                  | object    | Variation image data. See [Product variation - Image properties](#product-variation-image-properties)                                                                                                                                         |
| `attributes`             | array     | List of attributes. See [Product variation - Attributes properties](#product-variation-attributes-properties)                                                                                                                                 |
| `menu_order`             | integer   | Menu order, used to custom sort products.                                                                                                                                                                                                     |   
| `meta_data`              | array     | Meta data. See [Product variation - Meta data properties](#product-variation-meta-data-properties)                                                                                                                                            |
| `purchase_price`         | number    | Product's purchase price. <i class="label label-atum">ATUM</i>                                                                                                                                                                                |
| `supplier_id`            | integer   | The ID of the ATUM Supplier that is linked to this product. <i class="label label-atum">ATUM</i>                                                                                                                                              |
| `supplier_sku`           | string    | The Supplier's SKU for this product. <i class="label label-atum">ATUM</i>                                                                                                                                                                     |
| `barcode`                | string    | The barcode for this product. <i class="label label-atum">ATUM</i>                                                                                                                                                                            |
| `atum_controlled`        | boolean   | Whether this product is being controlled by ATUM. Default is `false`. <i class="label label-atum">ATUM</i>                                                                                                                                    |
| `out_stock_date`         | date-time | The date when this product run out of stock. <i class="label label-atum">ATUM</i>                                                                                                                                                             |
| `out_stock_threshold`    | number    | Out of stock threshold at product level. <i class="label label-atum">ATUM</i>                                                                                                                                                                 |
| `inbound_stock`          | number    | Product's inbound stock. <i class="label label-atum">ATUM</i>                                                                                                                                                                                 |
| `stock_on_hold`          | number    | Product's stock on hold. <i class="label label-atum">ATUM</i>                                                                                                                                                                                 |
| `sold_today`             | number    | Units sold today. <i class="label label-atum">ATUM</i>                                                                                                                                                                                        |
| `sales_last_days`        | number    | Sales the last 14 days. <i class="label label-atum">ATUM</i>                                                                                                                                                                                  |
| `reserved_stock`         | number    | Stock set as 'reserved_stock' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                     |
| `customer_returns`       | number    | Stock set as 'customer returns' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                   |
| `warehouse_damage`       | number    | Stock set as 'warehouse damage' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                   |
| `lost_in_post`           | number    | Stock set as 'lost in post' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                       |
| `other_logs`             | number    | Stock set as 'other' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                              |
| `out_stock_days`         | integer   | The number of days that the product is Out of stock. <i class="label label-atum">ATUM</i>                                                                                                                                                     |
| `lost_sales`             | number    | Product lost sales. <i class="label label-atum">ATUM</i>                                                                                                                                                                                      |
| `update_date`            | date-time | Last date when the ATUM product data was calculated and saved for this product. <i class="label label-atum">ATUM</i>                                                                                                                          |
| `mi_inventories`         | array     | An array of inventory IDs linked to the product (if any). <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i> <i class="label label-info">read-only</i>                                                     |
| `multi_inventory`        | string    | The Multi Inventory status for this product. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                                            |
| `inventory_sorting_mode` | string    | The sorting mode specified for inventory selling priority. Options: `fifo`, `lifo`, `bbe`, `manual`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                          |
| `inventory_iteration`    | string    | What to do when the first selling inventory runs out of stock. Options: `use_next`, `out_of_stock`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                           |
| `expirable_inventories`  | string    | Set the inventories as 'Out of Stock' when reaching their BBE dates. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                    |
| `price_per_inventory`    | string    | Allow distinct inventories to have distinct prices. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                                     |
| `linked_bom`             | array     | The BOM linked to the product with their quantities. See [Product - Linked BOM properties](#product-variation-linked-bom-properties-atum-product-levels) <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i> |
| `bom_sellable`           | array     | If the product is a BOM, indicates whether the product is sellable. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                                      |
| `minimum_threshold`      | number    | If the product is a BOM, indicates the product's minimum threshold. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                                      |
| `available_to_purchase`  | number    | If the product is a BOM, indicates the product's available to purchase amount. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                           |
| `selling_priority`       | integer   | If the product is a BOM, indicates the product's selling priority. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                                       |
| `calculated_stock`       | number    | If the BOM stock control is enabled and the product has linked BOM, it indicates the calculated stock quantity. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                          |
| `sync_purchase_price`    | boolean   | Whether to sync the product's purchase price with the BOM's purchase price. Default is `false`, <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                          |

### Product variation - Downloads properties ###

| Attribute | Type   | Description |
|-----------|--------|-------------|
| `id`      | string | File ID.    |
| `name`    | string | File name.  |
| `file`    | string | File URL.   |

### Product variation - Dimensions properties ###

| Attribute | Type   | Description       |
|-----------|--------|-------------------|
| `length`  | string | Variation length. |
| `width`   | string | Variation width.  |
| `height`  | string | Variation height. |

### Product variation - Image properties ###

| Attribute           | Type      | Description                                                                                             |
|---------------------|-----------|---------------------------------------------------------------------------------------------------------|
| `id`                | integer   | Image ID.                                                                                               |
| `date_created`      | date-time | The date the image was created, in the site's timezone. <i class="label label-info">read-only</i>       |
| `date_created_gmt`  | date-time | The date the image was created, as GMT. <i class="label label-info">read-only</i>                       |
| `date_modified`     | date-time | The date the image was last modified, in the site's timezone. <i class="label label-info">read-only</i> |
| `date_modified_gmt` | date-time | The date the image was last modified, as GMT. <i class="label label-info">read-only</i>                 |
| `src`               | string    | Image URL.                                                                                              |
| `name`              | string    | Image name.                                                                                             |
| `alt`               | string    | Image alternative text.                                                                                 |

### Product variation - Attributes properties ###

| Attribute | Type    | Description                   |
|-----------|---------|-------------------------------|
| `id`      | integer | Attribute ID.                 |
| `name`    | string  | Attribute name.               |
| `option`  | string  | Selected attribute term name. |

### Product variation - Meta data properties ###

| Attribute | Type    | Description                                        |
|-----------|---------|----------------------------------------------------|
| `id`      | integer | Meta ID. <i class="label label-info">read-only</i> |
| `key`     | string  | Meta key.                                          |
| `value`   | string  | Meta value.                                        |

### Product variation - Linked BOM properties <i class="label label-atum">ATUM</i> <i class="label label-addon">Product Levels</i> ###

| Attribute  | Type    | Description                                                                                   |
|------------|---------|-----------------------------------------------------------------------------------------------|
| `bom_id`   | integer | The linked BOM product ID.                                                                    |
| `bom_type` | string  | The linked BOM product type. Options: `raw_material`, `product_part`                          |
| `qty`      | number  | The linked BOM quantity.                                                                      |
| `delete`   | boolean | Whether to delete the linked BOM from the product. <i class="label label-info">write-only</i> |

## Create a product variation ##

This API helps you to create a new product variation.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations</h6>
	</div>
</div>

> JSON response example:

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/22/variations \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "regular_price": "9.00",
  "purchase_price": 6.5,
  "atum_controlled": true,
  "image": {
    "id": 48
  },
  "attributes": [
    {
      "id": 1,
      "name": "color",
      "option": "Purple"
    }
  ]
}'
```

```javascript
const data = {
   regular_price: "9.00",
   purchase_price: 6.5,
   atum_controlled: true,
   image: {
     id: 48
   },
   attributes: [
     {
       id: 1,
       name: "color",
       option: "Purple"
     }
   ]
};

WooCommerce.post("products/22/variations", data)
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
    'regular_price' => '9.00',
    'purchase_price' => 6.5,
    'atum_controlled' => true,
    'image' => [
        'id' => 48
    ],
    'attributes' => [
    [
        'id' => 1,
        'name' => 'color',
        'option' => 'Purple'
    ]
  ]
];

print_r($woocommerce->post('products/22/variations', $data));
?>
```

```python
data = {
  "regular_price": "9.00",
  "purchase_price": 6.5,
  "atum_controlled": true,
  "image": {
    "id": 48
  },
  "attributes": [
    {
      "id": 1,
      "name": "color",
      "option": "Purple"
    }
  ]
}

print(wcapi.post("products/22/variations", data).json())
```

```ruby
data = {
  regular_price: "9.00",
  purchase_price: 6.5,
  atum_controlled: true,
  image: {
    id: 48
  },
  attributes: [
    {
      id: 1,
      name: "color",
      option: "Purple"
    }
  ]
}

woocommerce.post("products/22/variations", data).parsed_response
```

> JSON response example:

```json
{
    "id": 2131,
    "date_created": "2019-11-08T09:00:34",
    "date_created_gmt": "2019-11-08T08:00:34",
    "date_modified": "2019-11-08T09:00:34",
    "date_modified_gmt": "2019-11-08T08:00:34",
    "description": "",
    "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
    "sku": "",
    "price": "9.00",
    "regular_price": "9.00",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "on_sale": false,
    "status": "publish",
    "purchasable": true,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": "parent",
    "stock_quantity": 0,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_class": "",
    "shipping_class_id": 0,
    "image": {
        "id": 48,
        "date_created": "2013-06-07T13:01:23",
        "date_created_gmt": "2013-06-07T11:01:23",
        "date_modified": "2013-06-07T13:01:23",
        "date_modified_gmt": "2013-06-07T11:01:23",
        "src": "https://example.com/wp-content/uploads/2013/06/hoodie_2_front.jpg",
        "name": "hoodie_2_front",
        "alt": ""
    },
    "attributes": [
        {
            "id": 1,
            "name": "color",
            "option": "Purple"
        }
    ],
    "menu_order": 0,
    "meta_data": [],
    "purchase_price": 6.5,
    "supplier_id": 0,
    "supplier_sku": "",
    "barcode": "",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inbound_stock": null,
    "stock_on_hold": null,
    "sold_today": null,
    "sales_last_days": null,
    "reserved_stock": null,
    "customer_returns": null,
    "warehouse_damage": null,
    "lost_in_post": null,
    "other_logs": null,
    "out_stock_days": null,
    "lost_sales": null,
    "update_date": "2019-11-08T07:00:34",
    "linked_bom": [],
    "sync_purchase_price": false,
    "mi_inventories": [],
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations/2131"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22"
            }
        ]
    }
}
```

## Retrieve a product variation ##

This API lets you retrieve and view a specific product variation by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/22/variations/23 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/22/variations/23")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/22/variations/23')); ?>
```

```python
print(wcapi.get("products/22/variations/23").json())
```

```ruby
woocommerce.get("products/22/variations/23").parsed_response
```

> JSON response example:

```json
{
    "id": 23,
    "date_created": "2013-06-07T12:44:57",
    "date_created_gmt": "2013-06-07T10:44:57",
    "date_modified": "2019-11-08T09:00:04",
    "date_modified_gmt": "2019-11-08T08:00:04",
    "description": "",
    "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=black",
    "sku": "",
    "price": "20",
    "regular_price": "20",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "on_sale": false,
    "status": "publish",
    "purchasable": true,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": "parent",
    "stock_quantity": 9,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_class": "",
    "shipping_class_id": 0,
    "image": {
        "id": 29,
        "date_created": "2013-06-07T12:45:30",
        "date_created_gmt": "2013-06-07T10:45:30",
        "date_modified": "2013-06-07T12:45:30",
        "date_modified_gmt": "2013-06-07T10:45:30",
        "src": "https://example.com/wp-content/uploads/2013/06/T_4_front1.jpg",
        "name": "T_4_front",
        "alt": ""
    },
    "attributes": [
        {
            "id": 1,
            "name": "color",
            "option": "Black"
        }
    ],
    "menu_order": 2,
    "meta_data": [],
    "purchase_price": 8,
    "supplier_id": 399,
    "supplier_sku": "",
    "barcode": "",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inbound_stock": 2,
    "stock_on_hold": 3,
    "sold_today": 0,
    "sales_last_days": 2,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "update_date": "2019-11-08T07:00:06",
    "linked_bom": [
        {
            "bom_id": 551,
            "bom_type": "raw_material",
            "qty": 1
        }
    ],
    "sync_purchase_price": false,
    "calculated_stock": 9,
    "mi_inventories": [],
    "multi_inventory": "no",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations/23"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22"
            }
        ]
    }
}
```

## List all product variations ##

This API helps you to view all the product variations.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/22/variations \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/22/variations")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/22/variations')); ?>
```

```python
print(wcapi.get("products/22/variations").json())
```

```ruby
woocommerce.get("products/22/variations").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 2131,
        "date_created": "2019-11-08T09:00:34",
        "date_created_gmt": "2019-11-08T08:00:34",
        "date_modified": "2019-11-08T09:00:59",
        "date_modified_gmt": "2019-11-08T08:00:59",
        "description": "",
        "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
        "sku": "",
        "price": "9.00",
        "regular_price": "9.00",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_from_gmt": null,
        "date_on_sale_to": null,
        "date_on_sale_to_gmt": null,
        "on_sale": false,
        "status": "publish",
        "purchasable": true,
        "virtual": false,
        "downloadable": false,
        "downloads": [],
        "download_limit": -1,
        "download_expiry": -1,
        "tax_status": "taxable",
        "tax_class": "",
        "manage_stock": "parent",
        "stock_quantity": 0,
        "stock_status": "outofstock",
        "backorders": "no",
        "backorders_allowed": false,
        "backordered": false,
        "weight": "",
        "dimensions": {
            "length": "",
            "width": "",
            "height": ""
        },
        "shipping_class": "",
        "shipping_class_id": 0,
        "image": {
            "id": 48,
            "date_created": "2013-06-07T13:01:23",
            "date_created_gmt": "2013-06-07T11:01:23",
            "date_modified": "2013-06-07T13:01:23",
            "date_modified_gmt": "2013-06-07T11:01:23",
            "src": "https://example.com/wp-content/uploads/2013/06/hoodie_2_front.jpg",
            "name": "hoodie_2_front",
            "alt": ""
        },
        "attributes": [
            {
                "id": 1,
                "name": "color",
                "option": "Purple"
            }
        ],
        "menu_order": 0,
        "meta_data": [],
        "purchase_price": 6.5,
        "supplier_id": 0,
        "supplier_sku": "",
        "barcode": "",
        "atum_controlled": false,
        "out_stock_date": null,
        "out_stock_threshold": 0,
        "inbound_stock": null,
        "stock_on_hold": null,
        "sold_today": null,
        "sales_last_days": null,
        "reserved_stock": null,
        "customer_returns": null,
        "warehouse_damage": null,
        "lost_in_post": null,
        "other_logs": null,
        "out_stock_days": null,
        "lost_sales": null,
        "update_date": "2019-11-08T07:00:59",
        "linked_bom": [],
        "sync_purchase_price": false,
        "mi_inventories": [],
        "multi_inventory": "global",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations/2131"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22"
                }
            ]
        }
    },
    {
        "id": 24,
        "date_created": "2013-06-07T12:44:58",
        "date_created_gmt": "2013-06-07T10:44:58",
        "date_modified": "2019-11-08T09:00:06",
        "date_modified_gmt": "2019-11-08T08:00:06",
        "description": "",
        "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=green",
        "sku": "",
        "price": "20",
        "regular_price": "20",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_from_gmt": null,
        "date_on_sale_to": null,
        "date_on_sale_to_gmt": null,
        "on_sale": false,
        "status": "publish",
        "purchasable": true,
        "virtual": false,
        "downloadable": false,
        "downloads": [],
        "download_limit": -1,
        "download_expiry": -1,
        "tax_status": "taxable",
        "tax_class": "",
        "manage_stock": true,
        "stock_quantity": 4,
        "stock_status": "instock",
        "backorders": "no",
        "backorders_allowed": false,
        "backordered": false,
        "weight": "",
        "dimensions": {
            "length": "",
            "width": "",
            "height": ""
        },
        "shipping_class": "",
        "shipping_class_id": 0,
        "image": {
            "id": 27,
            "date_created": "2013-06-07T12:45:27",
            "date_created_gmt": "2013-06-07T10:45:27",
            "date_modified": "2013-06-07T12:45:27",
            "date_modified_gmt": "2013-06-07T10:45:27",
            "src": "https://example.com/wp-content/uploads/2013/06/T_3_front.jpg",
            "name": "T_3_front",
            "alt": ""
        },
        "attributes": [
            {
                "id": 1,
                "name": "color",
                "option": "Green"
            }
        ],
        "menu_order": 2,
        "meta_data": [],
        "purchase_price": 12,
        "supplier_id": 386,
        "supplier_sku": "",
        "barcode": "",
        "atum_controlled": true,
        "out_stock_date": null,
        "out_stock_threshold": 0,
        "inbound_stock": 1,
        "stock_on_hold": 0,
        "sold_today": 0,
        "sales_last_days": 0,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 1,
        "other_logs": 1,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2019-11-08T07:00:06",
        "linked_bom": [],
        "sync_purchase_price": false,
        "mi_inventories": [],
        "multi_inventory": "no",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations/24"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22"
                }
            ]
        }
    },
    {
        "id": 23,
        "date_created": "2013-06-07T12:44:57",
        "date_created_gmt": "2013-06-07T10:44:57",
        "date_modified": "2019-11-08T09:00:04",
        "date_modified_gmt": "2019-11-08T08:00:04",
        "description": "",
        "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=black",
        "sku": "",
        "price": "20",
        "regular_price": "20",
        "sale_price": "",
        "date_on_sale_from": null,
        "date_on_sale_from_gmt": null,
        "date_on_sale_to": null,
        "date_on_sale_to_gmt": null,
        "on_sale": false,
        "status": "publish",
        "purchasable": true,
        "virtual": false,
        "downloadable": false,
        "downloads": [],
        "download_limit": -1,
        "download_expiry": -1,
        "tax_status": "taxable",
        "tax_class": "",
        "manage_stock": "parent",
        "stock_quantity": 9,
        "stock_status": "instock",
        "backorders": "no",
        "backorders_allowed": false,
        "backordered": false,
        "weight": "",
        "dimensions": {
            "length": "",
            "width": "",
            "height": ""
        },
        "shipping_class": "",
        "shipping_class_id": 0,
        "image": {
            "id": 29,
            "date_created": "2013-06-07T12:45:30",
            "date_created_gmt": "2013-06-07T10:45:30",
            "date_modified": "2013-06-07T12:45:30",
            "date_modified_gmt": "2013-06-07T10:45:30",
            "src": "https://example.com/wp-content/uploads/2013/06/T_4_front1.jpg",
            "name": "T_4_front",
            "alt": ""
        },
        "attributes": [
            {
                "id": 1,
                "name": "color",
                "option": "Black"
            }
        ],
        "menu_order": 2,
        "meta_data": [],
        "purchase_price": 8,
        "supplier_id": 399,
        "supplier_sku": "",
        "barcode": "",
        "atum_controlled": true,
        "out_stock_date": null,
        "out_stock_threshold": 0,
        "inbound_stock": 2,
        "stock_on_hold": 3,
        "sold_today": 0,
        "sales_last_days": 2,
        "reserved_stock": 0,
        "customer_returns": 0,
        "warehouse_damage": 0,
        "lost_in_post": 0,
        "other_logs": 0,
        "out_stock_days": 0,
        "lost_sales": 0,
        "update_date": "2019-11-08T07:00:06",
        "linked_bom": [
            {
                "bom_id": 551,
                "bom_type": "raw_material",
                "qty": 1
            }
        ],
        "sync_purchase_price": false,
        "calculated_stock": 9,
        "mi_inventories": [],
        "multi_inventory": "no",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations/23"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                }
            ],
            "up": [
                {
                    "href": "https://example.com/wp-json/wc/v3/products/22"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter                | Type    | Description                                                                                                                                                                                                       |
|--------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`                | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                                      |
| `page`                   | integer | Current page of the collection. Default is `1`.                                                                                                                                                                   |
| `per_page`               | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                                            |
| `search`                 | string  | Limit results to those matching a string.                                                                                                                                                                         |
| `after`                  | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                                       |
| `before`                 | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                                      |
| `modified_after`         | string  | Limit response to resources modified after a given ISO8601 compliant date.                                                                                                                                        |
| `modified_before`        | string  | Limit response to resources modified before a given ISO8601 compliant date.                                                                                                                                       |
| `exclude`                | array   | Ensure result set excludes specific IDs.                                                                                                                                                                          |
| `include`                | array   | Limit result set to specific ids.                                                                                                                                                                                 |
| `offset`                 | integer | Offset the result set by a specific number of items.                                                                                                                                                              |
| `order`                  | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                                       |
| `orderby`                | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                                     |
| `parent`                 | array   | Limit result set to those of particular parent IDs.                                                                                                                                                               |
| `parent_exclude`         | array   | Limit result set to all items except those of a particular parent ID.                                                                                                                                             |
| `slug`                   | string  | Limit result set to products with a specific slug.                                                                                                                                                                |
| `status`                 | string  | Limit result set to products assigned a specific status. Options: `any`, `draft`, `pending`, `private` and `publish`. Default is `any`.                                                                           |
| `sku`                    | string  | Limit result set to products with a specific SKU.                                                                                                                                                                 |
| `tax_class`              | string  | Limit result set to products with a specific tax class. Default options: `standard`, `reduced-rate` and `zero-rate`.                                                                                              |
| `on_sale`                | boolean | Limit result set to products on sale.                                                                                                                                                                             |
| `min_price`              | string  | Limit result set to products based on a minimum price.                                                                                                                                                            |
| `max_price`              | string  | Limit result set to products based on a maximum price.                                                                                                                                                            |
| `stock_status`           | string  | Limit result set to products with specified stock status. Options: `instock`, `outofstock` and `onbackorder`.                                                                                                     |
| `atum_controlled`        | boolean | Limit result set to products controlled by ATUM. <i class="label label-atum">ATUM</i>                                                                                                                             |
| `min_purchase_price`     | number  | Limit result set to products based on a minimum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `max_purchase_price`     | number  | Limit result set to products based on a maximum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `supplier`               | integer | Limit result set to products linked to the specified Supplier ID. <i class="label label-atum">ATUM</i>                                                                                                            |
| `supplier_sku`           | string  | Limit result set to products with a specific Supplier SKU. <i class="label label-atum">ATUM</i>                                                                                                                   |
| `barcode`                | string  | Limit result set to products with a specific barcode. <i class="label label-atum">ATUM</i>                                                                                                                        |
| `multi_inventory`        | string  | Limit result set to products with a specific Multi-Inventory status. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                     |
| `inventory_sorting_mode` | string  | Limit result set to products with a specific inventory sorting mode. Options: `fifo`, `lifo`, `bbe`, `manual` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i> |
| `inventory_iteration`    | string  | Limit result set to products with a specific inventory iteration. Options: `use_next`, `out_of_stock` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>         |
| `expirable_inventories`  | string  | Limit result set to products with a specific expirable inventories option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>               |
| `price_per_inventory`    | string  | Limit result set to products with a specific price per inventory option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                 |
| `bom_sellable`           | boolean | Limit result set to sellable BOM products. It should be used in conjunction with the `type` set to any BOM type. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>             |

## List all variations ##

This API helps you to view all the variations (no matter its parent product).

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/products-variations</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/products-variations \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/products-variations")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/products-variations')); ?>
```

```python
print(wcapi.get("atum/products-variations").json())
```

```ruby
woocommerce.get("atum/products-variations").parsed_response
```

> JSON response example:

```json
[
	{
		"id": 2969,
		"date_created": "2021-04-13T13:13:34",
		"date_created_gmt": "2021-04-13T11:13:34",
		"date_modified": "2021-04-13T13:20:12",
		"date_modified_gmt": "2021-04-13T11:20:12",
		"description": "",
		"permalink": "http://example.com/product/testing-variation-fields/?attribute_pa_color=orange",
		"sku": "",
		"price": "",
		"regular_price": "",
		"sale_price": "",
		"date_on_sale_from": null,
		"date_on_sale_from_gmt": null,
		"date_on_sale_to": null,
		"date_on_sale_to_gmt": null,
		"on_sale": false,
		"status": "publish",
		"purchasable": false,
		"virtual": false,
		"downloadable": false,
		"downloads": [],
		"download_limit": -1,
		"download_expiry": -1,
		"tax_status": "taxable",
		"tax_class": "",
		"manage_stock": true,
		"stock_quantity": 0,
		"stock_status": "outofstock",
		"backorders": "no",
		"backorders_allowed": false,
		"backordered": false,
		"low_stock_amount": "",
		"weight": "",
		"dimensions": {
			"length": "",
			"width": "",
			"height": ""
		},
		"shipping_class": "",
		"shipping_class_id": 0,
		"image": null,
		"attributes": [
			{
				"id": 1,
				"name": "color",
				"option": "Orange"
			}
		],
		"menu_order": 2,
		"meta_data": [],
		"purchase_price": null,
		"supplier_id": null,
		"supplier_sku": "",
		"barcode": "",
		"atum_controlled": true,
		"out_stock_date": null,
		"out_stock_threshold": null,
		"inbound_stock": null,
		"stock_on_hold": 0,
		"sold_today": 0,
		"sales_last_days": 0,
		"reserved_stock": null,
		"customer_returns": null,
		"warehouse_damage": null,
		"lost_in_post": null,
		"other_logs": null,
		"out_stock_days": 0,
		"lost_sales": 0,
		"update_date": "2021-04-21T05:39:48",
		"atum_stock_status": "outofstock",
		"low_stock": false,
		"linked_bom": [],
		"sync_purchase_price": false,
		"bom_sellable": null,
		"minimum_threshold": null,
		"available_to_purchase": null,
		"selling_priority": null,
		"calculated_stock": null,
		"is_bom": false,
		"mi_inventories": [],
		"multi_inventory": "global",
		"parent_id": 2966,
		"_links": {
			"self": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966/variations/2969"
				}
			],
			"collection": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966/variations"
				}
			],
			"up": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966"
				}
			]
		}
	},
	{
		"id": 2968,
		"date_created": "2021-04-13T13:13:34",
		"date_created_gmt": "2021-04-13T11:13:34",
		"date_modified": "2021-04-13T13:20:12",
		"date_modified_gmt": "2021-04-13T11:20:12",
		"description": "",
		"permalink": "http://example.com/product/testing-variation-fields/?attribute_pa_color=blue",
		"sku": "",
		"price": "",
		"regular_price": "",
		"sale_price": "",
		"date_on_sale_from": null,
		"date_on_sale_from_gmt": null,
		"date_on_sale_to": null,
		"date_on_sale_to_gmt": null,
		"on_sale": false,
		"status": "publish",
		"purchasable": false,
		"virtual": false,
		"downloadable": false,
		"downloads": [],
		"download_limit": -1,
		"download_expiry": -1,
		"tax_status": "taxable",
		"tax_class": "",
		"manage_stock": true,
		"stock_quantity": 0,
		"stock_status": "outofstock",
		"backorders": "no",
		"backorders_allowed": false,
		"backordered": false,
		"low_stock_amount": "",
		"weight": "",
		"dimensions": {
			"length": "",
			"width": "",
			"height": ""
		},
		"shipping_class": "",
		"shipping_class_id": 0,
		"image": null,
		"attributes": [
			{
				"id": 1,
				"name": "color",
				"option": "Blue"
			}
		],
		"menu_order": 1,
		"meta_data": [],
		"purchase_price": null,
		"supplier_id": null,
		"supplier_sku": "",
		"barcode": "",
		"atum_controlled": true,
		"out_stock_date": null,
		"out_stock_threshold": null,
		"inbound_stock": null,
		"stock_on_hold": 0,
		"sold_today": 0,
		"sales_last_days": 0,
		"reserved_stock": null,
		"customer_returns": null,
		"warehouse_damage": null,
		"lost_in_post": null,
		"other_logs": null,
		"out_stock_days": 0,
		"lost_sales": 0,
		"update_date": "2021-04-21T05:39:48",
		"atum_stock_status": "outofstock",
		"low_stock": false,
		"linked_bom": [],
		"sync_purchase_price": false,
		"bom_sellable": null,
		"minimum_threshold": null,
		"available_to_purchase": null,
		"selling_priority": null,
		"calculated_stock": null,
		"is_bom": false,
		"mi_inventories": [],
		"multi_inventory": "global",
		"parent_id": 2966,
		"_links": {
			"self": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966/variations/2968"
				}
			],
			"collection": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966/variations"
				}
			],
			"up": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/2966"
				}
			]
		}
	},
	{
		"id": 2889,
		"date_created": "2021-02-02T09:36:01",
		"date_created_gmt": "2021-02-02T08:36:01",
		"date_modified": "2021-02-02T09:37:51",
		"date_modified_gmt": "2021-02-02T08:37:51",
		"description": "",
		"permalink": "http://example.com/product/variable-test/?attribute_pa_color=purple",
		"sku": "",
		"price": "",
		"regular_price": "",
		"sale_price": "",
		"date_on_sale_from": null,
		"date_on_sale_from_gmt": null,
		"date_on_sale_to": null,
		"date_on_sale_to_gmt": null,
		"on_sale": false,
		"status": "publish",
		"purchasable": false,
		"virtual": false,
		"downloadable": false,
		"downloads": [],
		"download_limit": -1,
		"download_expiry": -1,
		"tax_status": "taxable",
		"tax_class": "",
		"manage_stock": "parent",
		"stock_quantity": 0,
		"stock_status": "outofstock",
		"backorders": "no",
		"backorders_allowed": false,
		"backordered": false,
		"low_stock_amount": "",
		"weight": "",
		"dimensions": {
			"length": "",
			"width": "",
			"height": ""
		},
		"shipping_class": "",
		"shipping_class_id": 0,
		"image": null,
		"attributes": [
			{
				"id": 1,
				"name": "color",
				"option": "Purple"
			}
		],
		"menu_order": 3,
		"meta_data": [],
		"purchase_price": null,
		"supplier_id": null,
		"supplier_sku": "",
		"barcode": "",
		"atum_controlled": false,
		"out_stock_date": null,
		"out_stock_threshold": null,
		"inbound_stock": null,
		"stock_on_hold": 0,
		"sold_today": 0,
		"sales_last_days": 0,
		"reserved_stock": null,
		"customer_returns": null,
		"warehouse_damage": null,
		"lost_in_post": null,
		"other_logs": null,
		"out_stock_days": 0,
		"lost_sales": 0,
		"update_date": "2021-04-21T05:39:48",
		"atum_stock_status": "outofstock",
		"low_stock": false,
		"linked_bom": [],
		"sync_purchase_price": false,
		"bom_sellable": null,
		"minimum_threshold": null,
		"available_to_purchase": null,
		"selling_priority": null,
		"calculated_stock": null,
		"is_bom": false,
		"mi_inventories": [],
		"multi_inventory": "global",
		"parent_id": 505,
		"_links": {
			"self": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/505/variations/2889"
				}
			],
			"collection": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/505/variations"
				}
			],
			"up": [
				{
					"href": "http://example.com/wp-json/wc/v3/products/505"
				}
			]
		}
	}
]
```

#### Available parameters ####

| Parameter                | Type    | Description                                                                                                                                                                                                       |
|--------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`                | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                                      |
| `page`                   | integer | Current page of the collection. Default is `1`.                                                                                                                                                                   |
| `per_page`               | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                                            |
| `search`                 | string  | Limit results to those matching a string.                                                                                                                                                                         |
| `after`                  | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                                       |
| `before`                 | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                                      |
| `modified_after`         | string  | Limit response to resources modified after a given ISO8601 compliant date.                                                                                                                                        |
| `modified_before`        | string  | Limit response to resources modified before a given ISO8601 compliant date.                                                                                                                                       |
| `exclude`                | array   | Ensure result set excludes specific IDs.                                                                                                                                                                          |
| `include`                | array   | Limit result set to specific ids.                                                                                                                                                                                 |
| `offset`                 | integer | Offset the result set by a specific number of items.                                                                                                                                                              |
| `order`                  | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                                       |
| `orderby`                | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                                     |
| `parent`                 | array   | Limit result set to those of particular parent IDs.                                                                                                                                                               |
| `parent_exclude`         | array   | Limit result set to all items except those of a particular parent ID.                                                                                                                                             |
| `slug`                   | string  | Limit result set to products with a specific slug.                                                                                                                                                                |
| `status`                 | string  | Limit result set to products assigned a specific status. Options: `any`, `draft`, `pending`, `private` and `publish`. Default is `any`.                                                                           |
| `sku`                    | string  | Limit result set to products with a specific SKU.                                                                                                                                                                 |
| `tax_class`              | string  | Limit result set to products with a specific tax class. Default options: `standard`, `reduced-rate` and `zero-rate`.                                                                                              |
| `on_sale`                | boolean | Limit result set to products on sale.                                                                                                                                                                             |
| `min_price`              | string  | Limit result set to products based on a minimum price.                                                                                                                                                            |
| `max_price`              | string  | Limit result set to products based on a maximum price.                                                                                                                                                            |
| `stock_status`           | string  | Limit result set to products with specified stock status. Options: `instock`, `outofstock` and `onbackorder`.                                                                                                     |
| `atum_controlled`        | boolean | Limit result set to products controlled by ATUM. <i class="label label-atum">ATUM</i>                                                                                                                             |
| `min_purchase_price`     | number  | Limit result set to products based on a minimum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `max_purchase_price`     | number  | Limit result set to products based on a maximum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `supplier`               | integer | Limit result set to products linked to the specified Supplier ID. <i class="label label-atum">ATUM</i>                                                                                                            |
| `supplier_sku`           | string  | Limit result set to products with a specific Supplier SKU. <i class="label label-atum">ATUM</i>                                                                                                                   |
| `barcode`                | string  | Limit result set to products with a specific barcode. <i class="label label-atum">ATUM</i>                                                                                                                        |
| `multi_inventory`        | string  | Limit result set to products with a specific Multi-Inventory status. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                     |
| `inventory_sorting_mode` | string  | Limit result set to products with a specific inventory sorting mode. Options: `fifo`, `lifo`, `bbe`, `manual` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i> |
| `inventory_iteration`    | string  | Limit result set to products with a specific inventory iteration. Options: `use_next`, `out_of_stock` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>         |
| `expirable_inventories`  | string  | Limit result set to products with a specific expirable inventories option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>               |
| `price_per_inventory`    | string  | Limit result set to products with a specific price per inventory option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                 |
| `bom_sellable`           | boolean | Limit result set to sellable BOM products. It should be used in conjunction with the `type` set to any BOM type. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>             |

## Update a product variation ##

This API lets you make changes to a product variation.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/products/22/variations/23 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "multi_inventory": "yes",
      "inventory_sorting_mode": "bbe",
      "inventory_iteration": "use_next",
      "expirable_inventories": "yes",
      "price_per_inventory": "yes"
    }'
```

```javascript
const data = {
   multi_inventory: "yes",
   inventory_sorting_mode: "bbe",
   inventory_iteration: "use_next",
   expirable_inventories: "yes",
   price_per_inventory: "yes"
 };

WooCommerce.put("products/22/variations/23", data)
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
  'multi_inventory' => 'yes',
  'inventory_sorting_mode' => 'bbe',
  'inventory_iteration' => 'use_next',
  'expirable_inventories' => 'yes',
  'price_per_inventory' => 'yes'
];

print_r($woocommerce->put('products/22/variations/23', $data));
?>
```

```python
data = {
     "multi_inventory": "yes",
     "inventory_sorting_mode": "bbe",
     "inventory_iteration": "use_next",
     "expirable_inventories": "yes",
     "price_per_inventory": "yes"
}

print(wcapi.put("products/22/variations/23", data).json())
```

```ruby
data = {
     multi_inventory: "yes",
     inventory_sorting_mode: "bbe",
     inventory_iteration: "use_next",
     expirable_inventories: "yes",
     price_per_inventory: "yes"
}

woocommerce.put("products/22/variations/23", data).parsed_response
```

> JSON response example:

```json
{
    "id": 23,
    "date_created": "2013-06-07T12:44:57",
    "date_created_gmt": "2013-06-07T10:44:57",
    "date_modified": "2019-11-08T10:22:13",
    "date_modified_gmt": "2019-11-08T09:22:13",
    "description": "",
    "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=black",
    "sku": "",
    "price": null,
    "regular_price": null,
    "sale_price": null,
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "on_sale": false,
    "status": "publish",
    "purchasable": true,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": true,
    "stock_quantity": 0,
    "stock_status": "outofstock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_class": "",
    "shipping_class_id": 0,
    "image": {
        "id": 29,
        "date_created": "2013-06-07T12:45:30",
        "date_created_gmt": "2013-06-07T10:45:30",
        "date_modified": "2013-06-07T12:45:30",
        "date_modified_gmt": "2013-06-07T10:45:30",
        "src": "https://example.com/wp-content/uploads/2013/06/T_4_front1.jpg",
        "name": "T_4_front",
        "alt": ""
    },
    "attributes": [
        {
            "id": 1,
            "name": "color",
            "option": "Black"
        }
    ],
    "menu_order": 2,
    "meta_data": [],
    "purchase_price": 8,
    "supplier_id": 399,
    "supplier_sku": "",
    "barcode": "",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inbound_stock": 2,
    "stock_on_hold": 3,
    "sold_today": 0,
    "sales_last_days": 2,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "update_date": "2019-11-08T07:00:06",
    "linked_bom": [
        {
            "bom_id": 551,
            "bom_type": "raw_material",
            "qty": 1
        }
    ],
    "sync_purchase_price": false,
    "calculated_stock": 9,
    "mi_inventories": [
        81
    ],
    "multi_inventory": "yes",
    "inventory_sorting_mode": "bbe",
    "inventory_iteration": "use_next",
    "expirable_inventories": "yes",
    "price_per_inventory": "yes",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations/23"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22"
            }
        ]
    }
}
```

## Delete a product variation ##

This API helps you delete a product variation.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/products/22/variations/2131?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("products/22/variations/2131", {
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
<?php print_r($woocommerce->delete('products/22/variations/2131', ['force' => true])); ?>
```

```python
print(wcapi.delete("products/22/variations/2131", params={"force": True}).json())
```

```ruby
woocommerce.delete("products/22/variations/2131", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 2131,
    "date_created": "2019-11-08T09:00:34",
    "date_created_gmt": "2019-11-08T08:00:34",
    "date_modified": "2019-11-08T09:00:59",
    "date_modified_gmt": "2019-11-08T08:00:59",
    "description": "",
    "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
    "sku": "",
    "price": "9.00",
    "regular_price": "9.00",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "on_sale": false,
    "status": "publish",
    "purchasable": true,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": "parent",
    "stock_quantity": 0,
    "stock_status": "outofstock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_class": "",
    "shipping_class_id": 0,
    "image": {
        "id": 48,
        "date_created": "2013-06-07T13:01:23",
        "date_created_gmt": "2013-06-07T11:01:23",
        "date_modified": "2013-06-07T13:01:23",
        "date_modified_gmt": "2013-06-07T11:01:23",
        "src": "https://example.com/wp-content/uploads/2013/06/hoodie_2_front.jpg",
        "name": "hoodie_2_front",
        "alt": ""
    },
    "attributes": [
        {
            "id": 1,
            "name": "color",
            "option": "Purple"
        }
    ],
    "menu_order": 0,
    "meta_data": [],
    "purchase_price": 6.5,
    "supplier_id": 0,
    "supplier_sku": "",
    "barcode": "",
    "atum_controlled": false,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inbound_stock": null,
    "stock_on_hold": null,
    "sold_today": null,
    "sales_last_days": null,
    "reserved_stock": null,
    "customer_returns": null,
    "warehouse_damage": null,
    "lost_in_post": null,
    "other_logs": null,
    "out_stock_days": null,
    "lost_sales": null,
    "update_date": "2019-11-08T07:00:59",
    "linked_bom": [],
    "sync_purchase_price": false,
    "mi_inventories": [],
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations/2131"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22/variations"
            }
        ],
        "up": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/22"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                   |
|-----------|--------|---------------------------------------------------------------|
| `force`   | string | Required to be `true`, as resource does not support trashing. |

## Batch update product variations ##

This API helps you to batch create, update and delete multiple product variations.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/&lt;product_id&gt;/variations/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/22/variations/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "create": [
    {
      "regular_price": "10.00",
      "atum_controlled": true,
      "attributes": [
        {
          "id": 1,
          "name": "color",
          "option": "Purple"
        }
      ]
    },
    {
      "regular_price": "11.00",
      "atum_controlled": true,
      "attributes": [
        {
          "id": 1,
          "name": "color",
          "option": "Orange"
        }
      ]
    }
  ],
  "update": [
    {
      "id": 24,
      "supplier_id": 399,
      "supplier_sku": "VARSKU"
    }
  ],
  "delete": [
    2132
  ]
}'
```

```javascript
const data = {
   create: [
     {
       regular_price: "10.00",
       atum_controlled: true,
       attributes: [
         {
           id: 1,
           name: "color",
           option: "Purple"
         }
       ]
     },
     {
       regular_price: "11.00",
       atum_controlled: true,
       attributes: [
         {
           id: 1,
           name: "color",
           option: "Orange"
         }
       ]
     }
   ],
   update: [
     {
       id: 24,
       supplier_id: 399,
       supplier_sku: "VARSKU"
     }
   ],
   delete: [
     2132
   ]
};

WooCommerce.post("products/22/variations/batch", data)
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
      'regular_price' => '10.00',
      'atum_controlled' => true,
      'attributes' => [
        [
          'id' => 1,
          'name' => 'color',
          'option' => 'Purple'
        ]
      ]
    ],
    [
      'regular_price' => '11.00',
      'atum_controlled' => true,
      'attributes' => [
        [
          'id' => 1,
          'name' => 'color',
          'option' => 'Orange'
        ]
      ]
    ]
  ],
  'update' => [
    [
      'id' => 24,
      'supplier_id' => 399,
      'supplier_sku' => 'VARSKU'
    ]
  ],
  'delete' => [
    2132
  ]
];

print_r($woocommerce->post('products/22/variations/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "regular_price": "10.00",
     "atum_controlled": true,
     "attributes": [
       {
         "id": 1,
         "name": "color",
         "option": "Purple"
       }
     ]
   },
   {
     "regular_price": "11.00",
     "atum_controlled": true,
     "attributes": [
       {
         "id": 1,
         "name": "color",
         "option": "Orange"
       }
     ]
   }
 ],
 "update": [
   {
     "id": 24,
     "supplier_id": 399,
     "supplier_sku": "VARSKU"
   }
 ],
 "delete": [
   2132
 ]
}

print(wcapi.post("products/22/variations/batch", data).json())
```

```ruby
data = {
  create: [
    {
      regular_price: "10.00",
      atum_controlled: true,
      attributes: [
        {
          id: 1,
          name: "color",
          option: "Purple"
        }
      ]
    },
    {
      regular_price: "11.00",
      atum_controlled: true,
      attributes: [
       {
          id: 1,
          name: "color",
          option: "Orange"
        }
      ]
    }
  ],
  update: [
    {
      id: 24,
      supplier_id: 399,
      supplier_sku: "VARSKU"
    }
  ],
  delete: [
    2132
  ]
}

woocommerce.post("products/22/variations/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2133,
            "date_created": "2019-11-08T10:52:24",
            "date_created_gmt": "2019-11-08T09:52:24",
            "date_modified": "2019-11-08T10:52:24",
            "date_modified_gmt": "2019-11-08T09:52:24",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
            "sku": "",
            "price": "10.00",
            "regular_price": "10.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 25,
                "date_created": "2013-06-07T12:45:14",
                "date_created_gmt": "2013-06-07T10:45:14",
                "date_modified": "2013-06-07T12:45:14",
                "date_modified_gmt": "2013-06-07T10:45:14",
                "src": "https://example.com/wp-content/uploads/2013/06/T_4_front.jpg",
                "name": "T_4_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Purple"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:52:25",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/2133"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        },
        {
            "id": 2134,
            "date_created": "2019-11-08T10:52:26",
            "date_created_gmt": "2019-11-08T09:52:26",
            "date_modified": "2019-11-08T10:52:26",
            "date_modified_gmt": "2019-11-08T09:52:26",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=orange",
            "sku": "",
            "price": "11.00",
            "regular_price": "11.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 25,
                "date_created": "2013-06-07T12:45:14",
                "date_created_gmt": "2013-06-07T10:45:14",
                "date_modified": "2013-06-07T12:45:14",
                "date_modified_gmt": "2013-06-07T10:45:14",
                "src": "https://example.com/wp-content/uploads/2013/06/T_4_front.jpg",
                "name": "T_4_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Orange"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:52:26",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/2134"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 24,
            "date_created": "2013-06-07T12:44:58",
            "date_created_gmt": "2013-06-07T10:44:58",
            "date_modified": "2019-11-08T10:52:27",
            "date_modified_gmt": "2019-11-08T09:52:27",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=green",
            "sku": "",
            "price": "20",
            "regular_price": "20",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": true,
            "stock_quantity": 4,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 27,
                "date_created": "2013-06-07T12:45:27",
                "date_created_gmt": "2013-06-07T10:45:27",
                "date_modified": "2013-06-07T12:45:27",
                "date_modified_gmt": "2013-06-07T10:45:27",
                "src": "https://example.com/wp-content/uploads/2013/06/T_3_front.jpg",
                "name": "T_3_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Green"
                }
            ],
            "menu_order": 2,
            "meta_data": [],
            "purchase_price": 12,
            "supplier_id": 399,
            "supplier_sku": "VARSKU",
            "barcode": "AAAAOOOOOOP",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": 1,
            "stock_on_hold": 0,
            "sold_today": 0,
            "sales_last_days": 0,
            "reserved_stock": 0,
            "customer_returns": 0,
            "warehouse_damage": 0,
            "lost_in_post": 1,
            "other_logs": 1,
            "out_stock_days": 0,
            "lost_sales": 0,
            "update_date": "2019-11-08T08:52:27",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "no",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/24"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 2132,
            "date_created": "2019-11-08T10:51:11",
            "date_created_gmt": "2019-11-08T09:51:11",
            "date_modified": "2019-11-08T10:51:11",
            "date_modified_gmt": "2019-11-08T09:51:11",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
            "sku": "",
            "price": "9.00",
            "regular_price": "9.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "outofstock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 48,
                "date_created": "2013-06-07T13:01:23",
                "date_created_gmt": "2013-06-07T11:01:23",
                "date_modified": "2013-06-07T13:01:23",
                "date_modified_gmt": "2013-06-07T11:01:23",
                "src": "https://example.com/wp-content/uploads/2013/06/hoodie_2_front.jpg",
                "name": "hoodie_2_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Purple"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 6.5,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:51:11",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0/variations/2132"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0"
                    }
                ]
            }
        }
    ]
}
```

## Batch update any variations ##

<i class="label label-ATUM">ATUM</i>

This API helps you to batch create, update and delete multiple product variations and also mixing variations from distinct variables at the same time.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/product-variations/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/product-variations/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "create": [
    {
      "product_id": 22,
      "regular_price": "10.00",
      "atum_controlled": true,
      "attributes": [
        {
          "id": 1,
          "name": "color",
          "option": "Purple"
        }
      ]
    },
    {
      "product_id": 22,
      "regular_price": "11.00",
      "atum_controlled": true,
      "attributes": [
        {
          "id": 1,
          "name": "color",
          "option": "Orange"
        }
      ]
    }
  ],
  "update": [
    {
      "id": 24,
      "supplier_id": 399,
      "supplier_sku": "VARSKU"
    }
  ],
  "delete": [
    2132
  ]
}'
```

```javascript
const data = {
   create: [
     {
       product_id: 22,
       regular_price: "10.00",
       atum_controlled: true,
       attributes: [
         {
           id: 1,
           name: "color",
           option: "Purple"
         }
       ]
     },
     {
       product_id: 22,
       regular_price: "11.00",
       atum_controlled: true,
       attributes: [
         {
           id: 1,
           name: "color",
           option: "Orange"
         }
       ]
     }
   ],
   update: [
     {
       id: 24,
       supplier_id: 399,
       supplier_sku: "VARSKU"
     }
   ],
   delete: [
     2132
   ]
};

WooCommerce.post("atum/product-variations/batch", data)
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
      'product_id' => 22,
      'regular_price' => '10.00',
      'atum_controlled' => true,
      'attributes' => [
        [
          'id' => 1,
          'name' => 'color',
          'option' => 'Purple'
        ]
      ]
    ],
    [
      'product_id' => 22,
      'regular_price' => '11.00',
      'atum_controlled' => true,
      'attributes' => [
        [
          'id' => 1,
          'name' => 'color',
          'option' => 'Orange'
        ]
      ]
    ]
  ],
  'update' => [
    [
      'id' => 24,
      'supplier_id' => 399,
      'supplier_sku' => 'VARSKU'
    ]
  ],
  'delete' => [
    2132
  ]
];

print_r($woocommerce->post('atum/product-variations/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "product_id": 22,
     "regular_price": "10.00",
     "atum_controlled": true,
     "attributes": [
       {
         "id": 1,
         "name": "color",
         "option": "Purple"
       }
     ]
   },
   {
     "product_id": 22,
     "regular_price": "11.00",
     "atum_controlled": true,
     "attributes": [
       {
         "id": 1,
         "name": "color",
         "option": "Orange"
       }
     ]
   }
 ],
 "update": [
   {
     "id": 24,
     "supplier_id": 399,
     "supplier_sku": "VARSKU"
   }
 ],
 "delete": [
   2132
 ]
}

print(wcapi.post("atum/product-variations/batch", data).json())
```

```ruby
data = {
  create: [
    {
      product_id: 22,
      regular_price: "10.00",
      atum_controlled: true,
      attributes: [
        {
          id: 1,
          name: "color",
          option: "Purple"
        }
      ]
    },
    {
      product_id: 22,
      regular_price: "11.00",
      atum_controlled: true,
      attributes: [
       {
          id: 1,
          name: "color",
          option: "Orange"
        }
      ]
    }
  ],
  update: [
    {
      id: 24,
      supplier_id: 399,
      supplier_sku: "VARSKU"
    }
  ],
  delete: [
    2132
  ]
}

woocommerce.post("products/22/variations/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2133,
            "date_created": "2019-11-08T10:52:24",
            "date_created_gmt": "2019-11-08T09:52:24",
            "date_modified": "2019-11-08T10:52:24",
            "date_modified_gmt": "2019-11-08T09:52:24",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
            "sku": "",
            "price": "10.00",
            "regular_price": "10.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 25,
                "date_created": "2013-06-07T12:45:14",
                "date_created_gmt": "2013-06-07T10:45:14",
                "date_modified": "2013-06-07T12:45:14",
                "date_modified_gmt": "2013-06-07T10:45:14",
                "src": "https://example.com/wp-content/uploads/2013/06/T_4_front.jpg",
                "name": "T_4_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Purple"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:52:25",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/2133"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        },
        {
            "id": 2134,
            "date_created": "2019-11-08T10:52:26",
            "date_created_gmt": "2019-11-08T09:52:26",
            "date_modified": "2019-11-08T10:52:26",
            "date_modified_gmt": "2019-11-08T09:52:26",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=orange",
            "sku": "",
            "price": "11.00",
            "regular_price": "11.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 25,
                "date_created": "2013-06-07T12:45:14",
                "date_created_gmt": "2013-06-07T10:45:14",
                "date_modified": "2013-06-07T12:45:14",
                "date_modified_gmt": "2013-06-07T10:45:14",
                "src": "https://example.com/wp-content/uploads/2013/06/T_4_front.jpg",
                "name": "T_4_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Orange"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:52:26",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/2134"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 24,
            "date_created": "2013-06-07T12:44:58",
            "date_created_gmt": "2013-06-07T10:44:58",
            "date_modified": "2019-11-08T10:52:27",
            "date_modified_gmt": "2019-11-08T09:52:27",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=green",
            "sku": "",
            "price": "20",
            "regular_price": "20",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": true,
            "stock_quantity": 4,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 27,
                "date_created": "2013-06-07T12:45:27",
                "date_created_gmt": "2013-06-07T10:45:27",
                "date_modified": "2013-06-07T12:45:27",
                "date_modified_gmt": "2013-06-07T10:45:27",
                "src": "https://example.com/wp-content/uploads/2013/06/T_3_front.jpg",
                "name": "T_3_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Green"
                }
            ],
            "menu_order": 2,
            "meta_data": [],
            "purchase_price": 12,
            "supplier_id": 399,
            "supplier_sku": "VARSKU",
            "barcode": "AAAAOOOOOOP",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": 1,
            "stock_on_hold": 0,
            "sold_today": 0,
            "sales_last_days": 0,
            "reserved_stock": 0,
            "customer_returns": 0,
            "warehouse_damage": 0,
            "lost_in_post": 1,
            "other_logs": 1,
            "out_stock_days": 0,
            "lost_sales": 0,
            "update_date": "2019-11-08T08:52:27",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "no",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations/24"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/22"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 2132,
            "date_created": "2019-11-08T10:51:11",
            "date_created_gmt": "2019-11-08T09:51:11",
            "date_modified": "2019-11-08T10:51:11",
            "date_modified_gmt": "2019-11-08T09:51:11",
            "description": "",
            "permalink": "https://example.com/product/ship-your-idea/?attribute_pa_color=purple",
            "sku": "",
            "price": "9.00",
            "regular_price": "9.00",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "on_sale": false,
            "status": "publish",
            "purchasable": true,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": "parent",
            "stock_quantity": 0,
            "stock_status": "outofstock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_class": "",
            "shipping_class_id": 0,
            "image": {
                "id": 48,
                "date_created": "2013-06-07T13:01:23",
                "date_created_gmt": "2013-06-07T11:01:23",
                "date_modified": "2013-06-07T13:01:23",
                "date_modified_gmt": "2013-06-07T11:01:23",
                "src": "https://example.com/wp-content/uploads/2013/06/hoodie_2_front.jpg",
                "name": "hoodie_2_front",
                "alt": ""
            },
            "attributes": [
                {
                    "id": 1,
                    "name": "color",
                    "option": "Purple"
                }
            ],
            "menu_order": 0,
            "meta_data": [],
            "purchase_price": 6.5,
            "supplier_id": 0,
            "supplier_sku": "",
            "barcode": "",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inbound_stock": null,
            "stock_on_hold": null,
            "sold_today": null,
            "sales_last_days": null,
            "reserved_stock": null,
            "customer_returns": null,
            "warehouse_damage": null,
            "lost_in_post": null,
            "other_logs": null,
            "out_stock_days": null,
            "lost_sales": null,
            "update_date": "2019-11-08T08:51:11",
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0/variations/2132"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0/variations"
                    }
                ],
                "up": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/0"
                    }
                ]
            }
        }
    ]
}
```
