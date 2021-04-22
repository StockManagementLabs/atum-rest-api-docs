# Products #

This endpoint is an extension of the official WC's orders enndpoint with extra info added by ATUM and/or its add-ons. 
You can identify the ATUM data with the corresponding labels.

The products API allows you to create, view, update, and delete individual, or a batch, of products.

## Product properties ##

| Attribute                    | Type      | Description                                                                                                                                                                                                                          |
|------------------------------|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                         | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                                        |
| `name`                       | string    | Product name.                                                                                                                                                                                                                        |
| `slug`                       | string    | Product slug.                                                                                                                                                                                                                        |
| `permalink`                  | string    | Product URL. <i class="label label-info">read-only</i>                                                                                                                                                                               |
| `date_created`               | date-time | The date the product was created, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                  |
| `date_created_gmt`           | date-time | The date the product was created, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                  |
| `date_modified`              | date-time | The date the product was last modified, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                            |
| `date_modified_gmt`          | date-time | The date the product was last modified, as GMT. <i class="label label-info">read-only</i>                                                                                                                                            |
| `type`                       | string    | Product type. Options: `simple`, `grouped`, `external`, `variable`, `product-part`, `raw-material`, `variable-product-part` and `variable-raw-material`. Default is `simple`.                                                        |
| `status`                     | string    | Product status (post status). Options: `draft`, `pending`, `private` and `publish`. Default is `publish`.                                                                                                                            |
| `featured`                   | boolean   | Featured product. Default is `false`.                                                                                                                                                                                                |
| `catalog_visibility`         | string    | Catalog visibility. Options: `visible`, `catalog`, `search` and `hidden`. Default is `visible`.                                                                                                                                      |
| `description`                | string    | Product description.                                                                                                                                                                                                                 |
| `short_description`          | string    | Product short description.                                                                                                                                                                                                           |
| `sku`                        | string    | Unique identifier.                                                                                                                                                                                                                   |
| `price`                      | string    | Current product price. <i class="label label-info">read-only</i>                                                                                                                                                                     |
| `regular_price`              | string    | Product regular price.                                                                                                                                                                                                               |
| `sale_price`                 | string    | Product sale price.                                                                                                                                                                                                                  |
| `date_on_sale_from`          | date-time | Start date of sale price, in the site's timezone.                                                                                                                                                                                    |
| `date_on_sale_from_gmt`      | date-time | Start date of sale price, as GMT.                                                                                                                                                                                                    |
| `date_on_sale_to`            | date-time | End date of sale price, in the site's timezone.                                                                                                                                                                                      |
| `date_on_sale_to_gmt`        | date-time | End date of sale price, as GMT.                                                                                                                                                                                                      |
| `price_html`                 | string    | Price formatted in HTML. <i class="label label-info">read-only</i>                                                                                                                                                                   |
| `on_sale`                    | boolean   | Shows if the product is on sale. <i class="label label-info">read-only</i>                                                                                                                                                           |
| `purchasable`                | boolean   | Shows if the product can be bought. <i class="label label-info">read-only</i>                                                                                                                                                        |
| `total_sales`                | integer   | Amount of sales. <i class="label label-info">read-only</i>                                                                                                                                                                           |
| `virtual`                    | boolean   | If the product is virtual. Default is `false`.                                                                                                                                                                                       |
| `downloadable`               | boolean   | If the product is downloadable. Default is `false`.                                                                                                                                                                                  |
| `downloads`                  | array     | List of downloadable files. See [Product - Downloads properties](#product-downloads-properties)                                                                                                                                      |
| `download_limit`             | integer   | Number of times downloadable files can be downloaded after purchase. Default is `-1`.                                                                                                                                                |
| `download_expiry`            | integer   | Number of days until access to downloadable files expires. Default is `-1`.                                                                                                                                                          |
| `external_url`               | string    | Product external URL. Only for external products.                                                                                                                                                                                    |
| `button_text`                | string    | Product external button text. Only for external products.                                                                                                                                                                            |
| `tax_status`                 | string    | Tax status. Options: `taxable`, `shipping` and `none`. Default is `taxable`.                                                                                                                                                         |
| `tax_class`                  | string    | Tax class.                                                                                                                                                                                                                           |
| `manage_stock`               | boolean   | Stock management at product level. Default is `false`.                                                                                                                                                                               |
| `stock_quantity`             | integer   | Stock quantity.                                                                                                                                                                                                                      |
| `stock_status`               | string    | Controls the stock status of the product. Options: `instock`, `outofstock`, `onbackorder`. Default is `instock`.                                                                                                                     |
| `backorders`                 | string    | If managing stock, this controls if backorders are allowed. Options: `no`, `notify` and `yes`. Default is `no`.                                                                                                                      |
| `backorders_allowed`         | boolean   | Shows if backorders are allowed. <i class="label label-info">read-only</i>                                                                                                                                                           |
| `backordered`                | boolean   | Shows if the product is on backordered. <i class="label label-info">read-only</i>                                                                                                                                                    |
| `sold_individually`          | boolean   | Allow one item to be bought in a single order. Default is `false`.                                                                                                                                                                   |
| `weight`                     | string    | Product weight.                                                                                                                                                                                                                      |
| `dimensions`                 | object    | Product dimensions. See [Product - Dimensions properties](#product-dimensions-properties)                                                                                                                                            |
| `shipping_required`          | boolean   | Shows if the product need to be shipped. <i class="label label-info">read-only</i>                                                                                                                                                   |
| `shipping_taxable`           | boolean   | Shows whether or not the product shipping is taxable. <i class="label label-info">read-only</i>                                                                                                                                      |
| `shipping_class`             | string    | Shipping class slug.                                                                                                                                                                                                                 |
| `shipping_class_id`          | integer   | Shipping class ID. <i class="label label-info">read-only</i>                                                                                                                                                                         |
| `reviews_allowed`            | boolean   | Allow reviews. Default is `true`.                                                                                                                                                                                                    |
| `average_rating`             | string    | Reviews average rating. <i class="label label-info">read-only</i>                                                                                                                                                                    |
| `rating_count`               | integer   | Amount of reviews that the product have. <i class="label label-info">read-only</i>                                                                                                                                                   |
| `related_ids`                | array     | List of related products IDs. <i class="label label-info">read-only</i>                                                                                                                                                              |
| `upsell_ids`                 | array     | List of up-sell products IDs.                                                                                                                                                                                                        |
| `cross_sell_ids`             | array     | List of cross-sell products IDs.                                                                                                                                                                                                     |
| `parent_id`                  | integer   | Product parent ID.                                                                                                                                                                                                                   |
| `purchase_note`              | string    | Optional note to send the customer after purchase.                                                                                                                                                                                   |
| `categories`                 | array     | List of categories. See [Product - Categories properties](#product-categories-properties)                                                                                                                                            |
| `tags`                       | array     | List of tags. See [Product - Tags properties](#product-tags-properties)                                                                                                                                                              |
| `images`                     | array     | List of images. See [Product - Images properties](#product-images-properties)                                                                                                                                                        |
| `attributes`                 | array     | List of attributes. See [Product - Attributes properties](#product-attributes-properties)                                                                                                                                            |
| `default_attributes`         | array     | Defaults variation attributes. See [Product - Default attributes properties](#product-default-attributes-properties)                                                                                                                 |
| `variations`                 | array     | List of variations IDs. <i class="label label-info">read-only</i>                                                                                                                                                                    |
| `grouped_products`           | array     | List of grouped products ID.                                                                                                                                                                                                         |
| `menu_order`                 | integer   | Menu order, used to custom sort products.                                                                                                                                                                                            |
| `meta_data`                  | array     | Meta data. See [Product - Meta data properties](#product-meta-data-properties)                                                                                                                                                       |
| `purchase_price`             | number    | Product's purchase price. <i class="label label-atum">ATUM</i>                                                                                                                                                                       |
| `supplier_id`                | integer   | The ID of the ATUM Supplier that is linked to this product. <i class="label label-atum">ATUM</i>                                                                                                                                     |
| `supplier_sku`               | string    | The Supplier's SKU for this product. <i class="label label-atum">ATUM</i>                                                                                                                                                            |
| `atum_controlled`            | boolean   | Whether this product is being controlled by ATUM. Default is `false`. <i class="label label-atum">ATUM</i>                                                                                                                           |
| `out_stock_date`             | date-time | The date when this product run out of stock. <i class="label label-atum">ATUM</i>                                                                                                                                                    |
| `out_stock_threshold`        | number    | Out of stock threshold at product level. <i class="label label-atum">ATUM</i>                                                                                                                                                        |
| `inheritable`                | boolean   | Whether this product may have children. Default is `false`. <i class="label label-atum">ATUM</i>                                                                                                                                     |
| `inbound_stock`              | number    | Product's inbound stock. <i class="label label-atum">ATUM</i>                                                                                                                                                                        |
| `stock_on_hold`              | number    | Product's stock on hold. <i class="label label-atum">ATUM</i>                                                                                                                                                                        |
| `sold_today`                 | number    | Units sold today. <i class="label label-atum">ATUM</i>                                                                                                                                                                               |
| `sales_last_days`            | number    | Sales the last 14 days. <i class="label label-atum">ATUM</i>                                                                                                                                                                         |
| `reserved_stock`             | number    | Stock set as 'reserved_stock' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                            |
| `customer_returns`           | number    | Stock set as 'customer returns' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                          |
| `warehouse_damage`           | number    | Stock set as 'warehouse damage' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                          |
| `lost_in_post`               | number    | Stock set as 'lost in post' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                              |
| `other_logs`                 | number    | Stock set as 'other' within Inventory Logs. <i class="label label-atum">ATUM</i>                                                                                                                                                     |
| `out_stock_days`             | integer   | The number of days that the product is Out of stock. <i class="label label-atum">ATUM</i>                                                                                                                                            |
| `lost_sales`                 | number    | Product lost sales. <i class="label label-atum">ATUM</i>                                                                                                                                                                             |
| `has_location`               | boolean   | Whether this product has any ATUM location set. <i class="label label-atum">ATUM</i>                                                                                                                                                 |
| `update_date`                | date-time | Last date when the ATUM product data was calculated and saved for this product. <i class="label label-atum">ATUM</i>                                                                                                                 |
| `atum_locations`             | array     | List of categories. See [Product - ATUM locations properties](#product-atum-locations-properties-atum) <i class="label label-atum">ATUM</i>                                                                                          |
| `mi_inventories`             | array     | An array of inventory IDs linked to the product (if any). <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i> <i class="label label-info">read-only</i>                                            |
| `multi_inventory`            | string    | The Multi Inventory status for this product. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                                   |
| `inventory_sorting_mode`     | string    | The sorting mode specified for inventory selling priority. Options: `fifo`, `lifo`, `bbe`, `manual`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                 |
| `inventory_iteration`        | string    | What to do when the first selling inventory runs out of stock. Options: `use_next`, `out_of_stock`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                  |
| `expirable_inventories`      | string    | Set the inventories as 'Out of Stock' when reaching their BBE dates. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                           |
| `price_per_inventory`        | string    | Allow distinct inventories to have distinct prices. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                            |
| `selectable_inventories`     | string    | Whether the selectable inventories is enabled. Options: `yes`, `no`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                                 |
| `selectable_inventories_mode`| string    | The inventory selection mode for the frontend display. Options: `dropdown`, `list`, `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                                                  |
| `linked_bom`                 | array     | The BOM linked to the product with their quantities. See [Product - Linked BOM properties](#product-linked-bom-properties-atum-product-levels) <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>  |
| `bom_sellable`               | array     | If the product is a BOM, indicates whether the product is sellable. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                             |
| `minimum_threshold`          | number    | If the product is a BOM, indicates the product's minimum threshold. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                             |
| `available_to_purchase`      | number    | If the product is a BOM, indicates the product's available to purchase amount. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                  |
| `selling_priority`           | integer   | If the product is a BOM, indicates the product's selling priority. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                                              |
| `calculated_stock`           | number    | If the BOM stock control is enabled and the product has linked BOM, it indicates the calculated stock quantity. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                 |
| `sync_purchase_price`        | boolean   | Whether to sync the product's purchase price with the BOM's purchase price. Default is `false`, <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>                                                 |

### Product - Downloads properties ###

| Attribute | Type   | Description |
|-----------|--------|-------------|
| `id`      | string | File ID.    |
| `name`    | string | File name.  |
| `file`    | string | File URL.   |

### Product - Dimensions properties ###

| Attribute | Type   | Description     |
|-----------|--------|-----------------|
| `length`  | string | Product length. |
| `width`   | string | Product width.  |
| `height`  | string | Product height. |

### Product - Categories properties ###

| Attribute | Type    | Description                                              |
|-----------|---------|----------------------------------------------------------|
| `id`      | integer | Category ID.                                             |
| `name`    | string  | Category name. <i class="label label-info">read-only</i> |
| `slug`    | string  | Category slug. <i class="label label-info">read-only</i> |

### Product - Tags properties ###

| Attribute | Type    | Description                                         |
|-----------|---------|-----------------------------------------------------|
| `id`      | integer | Tag ID.                                             |
| `name`    | string  | Tag name. <i class="label label-info">read-only</i> |
| `slug`    | string  | Tag slug. <i class="label label-info">read-only</i> |

### Product - Images properties ###

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

### Product - Attributes properties ###

| Attribute   | Type    | Description                                                                                                       |
|-------------|---------|-------------------------------------------------------------------------------------------------------------------|
| `id`        | integer | Attribute ID.                                                                                                     |
| `name`      | string  | Attribute name.                                                                                                   |
| `position`  | integer | Attribute position.                                                                                               |
| `visible`   | boolean | Define if the attribute is visible on the "Additional information" tab in the product's page. Default is `false`. |
| `variation` | boolean | Define if the attribute can be used as variation. Default is `false`.                                             |
| `options`   | array   | List of available term names of the attribute.                                                                    |

### Product - Default attributes properties ###

| Attribute | Type    | Description                   |
|-----------|---------|-------------------------------|
| `id`      | integer | Attribute ID.                 |
| `name`    | string  | Attribute name.               |
| `option`  | string  | Selected attribute term name. |

### Product - Meta data properties ###

| Attribute | Type    | Description                                        |
|-----------|---------|----------------------------------------------------|
| `id`      | integer | Meta ID. <i class="label label-info">read-only</i> |
| `key`     | string  | Meta key.                                          |
| `value`   | string  | Meta value.                                        |

### Product - ATUM locations properties <i class="label label-atum">ATUM</i> ###

| Attribute | Type    | Description                                              |
|-----------|---------|----------------------------------------------------------|
| `id`      | integer | Location ID.                                             |
| `name`    | string  | Location name. <i class="label label-info">read-only</i> |
| `slug`    | string  | Location slug. <i class="label label-info">read-only</i> |

### Product - Linked BOM properties <i class="label label-atum">ATUM</i> <i class="label label-addon">Product Levels</i> ###

| Attribute  | Type    | Description                                                                                   |
|------------|---------|-----------------------------------------------------------------------------------------------|
| `bom_id`   | integer | The linked BOM product ID.                                                                    |
| `bom_type` | string  | The linked BOM product type. Options: `raw_material`, `product_part`                          |
| `qty`      | number  | The linked BOM quantity.                                                                      |
| `delete`   | boolean | Whether to delete the linked BOM from the product. <i class="label label-info">write-only</i> |

## Create a product ##

This API helps you to create a new product.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products</h6>
	</div>
</div>

> Example of how to create a `simple` product with ATUM data:

```shell
curl -X POST https://example.com/wp-json/wc/v3/products \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "name": "ATUM Test Product",
  "type": "simple",
  "regular_price": "21.99",
  "purchase_price": 15.2,
  "supplier_id": 399,
  "supplier_sku": "TEST1",
  "atum_controlled": true,
  "linked_bom": [
    {
      "bom_id": 175,
      "bom_type": "product_part",
      "qty": 3
    }
  ],
  "atum_locations": [
    {
      "id": 39
    },
    {
      "id": 37
    }
  ],
  "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  "categories": [
    {
      "id": 9
    },
    {
      "id": 14
    }
  ],
  "images": [
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
    },
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
    }
  ]
}'
```

```javascript
const data = {
  name: "ATUM Test Product",
  type: "simple",
  regular_price: "21.99",
  purchase_price: 15.2,
  supplier_id: 399,
  supplier_sku: "TEST1",
  atum_controlled: true,
  linked_bom: [
    {
      bom_id: 175,
      bom_type: "product_part",
      qty: 3
    }
  ],
  atum_locations: [
    {
      id: 39
    },
    {
      id: 37
    }
  ],
  description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  categories: [
    {
      id: 9
    },
    {
      id: 14
    }
  ],
  images: [
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
    }
  ]
};

WooCommerce.post("products", data)
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
    'name' => 'ATUM Test Product',
    'type' => 'simple',
    'regular_price' => '21.99',
    'purchase_price' => 15.2,
    'supplier_id' => 399,
    'supplier_sku' => 'TEST1',
    'atum_controlled' => true,
    'linked_bom' => [
        [
            'bom_id' => 175,
            'bom_type' => 'product_part',
            'qty' => 3
        ]
    ],
    'atum_locations' => [
        [
            'id' => 39
        ],
        [
            'id' => 37
        ]
    ],
    'description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.',
    'short_description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.',
    'categories' => [
        [
            'id' => 9
        ],
        [
            'id' => 14
        ]
    ],
    'images' => [
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg'
        ],
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg'
        ]
    ]
];

print_r($woocommerce->post('products', $data));
?>
```

```python
data = {
    "name": "ATUM Test Product",
    "type": "simple",
    "regular_price": "21.99",
    "purchase_price": 15.2,
    "supplier_id": 399,
    "supplier_sku": "TEST1",
    "atum_controlled": true,
    "linked_bom": [
      {
        "bom_id": 175,
        "bom_type": "product_part",
        "qty": 3
      }
    ],
    "atum_locations": [
      {
        "id": 39
      },
      {
        "id": 37
      }
    ],
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
    "categories": [
        {
            "id": 9
        },
        {
            "id": 14
        }
    ],
    "images": [
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
        },
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
        }
    ]
}

print(wcapi.post("products", data).json())
```

```ruby
data = {
  name: "ATUM Test Product",
  type: "simple",
  regular_price: "21.99",
  purchase_price: 15.2,
  supplier_id: 399,
  supplier_sku: "TEST1",
  atum_controlled: true,
  linked_bom: [
      {
          bom_id: 175,
          bom_type: "product_part",
          qty: 3
      }
  ],
  atum_locations: [
    {
        id: 39
    },
    {
        id: 37
    }
  ],
  description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  categories: [
    {
      id: 9
    },
    {
      id: 14
    }
  ],
  images: [
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg",
    }
  ]
}

woocommerce.post("products", data).parsed_response
```

> JSON response example:

```json
{
    "id": 1998,
    "name": "ATUM Test Product",
    "slug": "atum-test-product",
    "permalink": "https://example.com/product/atum-test-product/",
    "date_created": "2019-11-06T08:54:04",
    "date_created_gmt": "2019-11-06T07:54:04",
    "date_modified": "2019-11-06T08:54:04",
    "date_modified_gmt": "2019-11-06T07:54:04",
    "type": "simple",
    "status": "publish",
    "featured": false,
    "catalog_visibility": "visible",
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
    "sku": "",
    "price": "21.99",
    "regular_price": "21.99",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>21,99</span>",
    "on_sale": false,
    "purchasable": true,
    "total_sales": 0,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "external_url": "",
    "button_text": "",
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": false,
    "stock_quantity": null,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "sold_individually": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_required": true,
    "shipping_taxable": true,
    "shipping_class": "",
    "shipping_class_id": 0,
    "reviews_allowed": true,
    "average_rating": "0",
    "rating_count": 0,
    "related_ids": [
        37,
        103,
        60,
        19,
        15
    ],
    "upsell_ids": [],
    "cross_sell_ids": [],
    "parent_id": 0,
    "purchase_note": "",
    "categories": [
        {
            "id": 9,
            "name": "Clothing",
            "slug": "clothing"
        },
        {
            "id": 14,
            "name": "T-shirts",
            "slug": "t-shirts"
        }
    ],
    "tags": [],
    "images": [
        {
            "id": 1996,
            "date_created": "2019-11-06T09:54:03",
            "date_created_gmt": "2019-11-06T07:54:03",
            "date_modified": "2019-11-06T09:54:03",
            "date_modified_gmt": "2019-11-06T07:54:03",
            "src": "https://example.com/wp-content/uploads/2019/11/T_2_front-8.jpg",
            "name": "T_2_front-8.jpg",
            "alt": ""
        },
        {
            "id": 1997,
            "date_created": "2019-11-06T09:54:04",
            "date_created_gmt": "2019-11-06T07:54:04",
            "date_modified": "2019-11-06T09:54:04",
            "date_modified_gmt": "2019-11-06T07:54:04",
            "src": "https://example.com/wp-content/uploads/2019/11/T_2_back-8.jpg",
            "name": "T_2_back-8.jpg",
            "alt": ""
        }
    ],
    "attributes": [],
    "default_attributes": [],
    "variations": [],
    "grouped_products": [],
    "menu_order": 0,
    "meta_data": [],
    "bundle_layout": "",
    "bundled_by": [],
    "bundled_items": [],
    "purchase_price": 15.2,
    "supplier_id": 399,
    "supplier_sku": "TEST1",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inheritable": false,
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
    "has_location": null,
    "update_date": "2019-11-06T06:54:12",
    "atum_locations": [
        {
            "id": 39,
            "name": "Italy",
            "slug": "italy"
        },
        {
            "id": 37,
            "name": "Spain",
            "slug": "spain"
        }
    ],
    "linked_bom": [
        {
            "bom_id": 175,
            "bom_type": "product_part",
            "qty": 3
        }
    ],
    "sync_purchase_price": false,
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/1998"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products"
            }
        ]
    }
}
```

> Example of how to create a `variable product part` product with global and non-global attributes:

```shell
curl -X POST https://example.com/wp-json/wc/v3/products \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "name": "ATUM BOM Test",
  "type": "variable-product-part",
  "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  "categories": [
    {
      "id": 9
    },
    {
      "id": 14
    }
  ],
  "images": [
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_front.jpg"
    },
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_back.jpg"
    },
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_front.jpg"
    },
    {
      "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_back.jpg"
    }
  ],
  "attributes": [
    {
      "id": 6,
      "position": 0,
      "visible": false,
      "variation": true,
      "options": [
        "Black",
        "Green"
      ]
    },
    {
      "name": "Size",
      "position": 0,
      "visible": true,
      "variation": true,
      "options": [
        "S",
        "M"
      ]
    }
  ],
  "default_attributes": [
    {
      "id": 6,
      "option": "Black"
    },
    {
      "name": "Size",
      "option": "S"
    }
  ]
}'
```

```javascript
const data = {
  name: "ATUM BOM Test",
  type: "variable-product-part",
  description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  categories: [
    {
      id: 9
    },
    {
      id: 14
    }
  ],
  images: [
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_back.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_back.jpg"
    }
  ],
  attributes: [
    {
      id: 6,
      position: 0,
      visible: true,
      variation: true,
      options: [
        "Black",
        "Green"
      ]
    },
    {
      name: "Size",
      position: 0,
      visible: false,
      variation: true,
      options: [
        "S",
        "M"
      ]
    }
  ],
  default_attributes: [
    {
      id: 6,
      option: "Black"
    },
    {
      name: "Size",
      option: "S"
    }
  ]
};

WooCommerce.post("products", data)
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
    'name' => 'ATUM BOM Test',
    'type' => 'variable-product-part',
    'description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.',
    'short_description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.',
    'categories' => [
        [
            'id' => 9
        ],
        [
            'id' => 14
        ]
    ],
    'images' => [
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_front.jpg'
        ],
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_back.jpg'
        ],
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_front.jpg'
        ],
        [
            'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_back.jpg'
        ]
    ],
    'attributes' => [
        [
            'id' => 6,
            'position' => 0,
            'visible' => false,
            'variation' => true,
            'options' => [
                'Black',
                'Green'
            ]
        ],
        [
            'name' => 'Size',
            'position' => 0,
            'visible' => true,
            'variation' => true,
            'options' => [
                'S',
                'M'
            ]
        ]
    ],
    'default_attributes' => [
        [
            'id' => 6,
            'option' => 'Black'
        ],
        [
            'name' => 'Size',
            'option' => 'S'
        ]
    ]
];

print_r($woocommerce->post('products', $data));
?>
```

```python
data = {
    "name": "ATUM BOM Test",
    "type": "variable-product-part",
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
    "categories": [
        {
            "id": 9
        },
        {
            "id": 14
        }
    ],
    "images": [
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_front.jpg"
        },
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_back.jpg"
        },
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_front.jpg"
        },
        {
            "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_back.jpg"
        }
    ],
    "attributes": [
        {
            "id": 6,
            "position": 0,
            "visible": False,
            "variation": True,
            "options": [
                "Black",
                "Green"
            ]
        },
        {
            "name": "Size",
            "position": 0,
            "visible": True,
            "variation": True,
            "options": [
                "S",
                "M"
            ]
        }
    ],
    "default_attributes": [
        {
            "id": 6,
            "option": "Black"
        },
        {
            "name": "Size",
            "option": "S"
        }
    ]
}

print(wcapi.post("products", data).json())
```

```ruby
data = {
  name: "ATUM BOM Test",
  type: "variable-product-part",
  description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
  categories: [
    {
      id: 9
    },
    {
      id: 14
    }
  ],
  images: [
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_4_back.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_front.jpg"
    },
    {
      src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_3_back.jpg"
    }
  ],
  attributes: [
    {
      id: 6,
      position: 0,
      visible: false,
      variation: true,
      options: [
        "Black",
        "Green"
      ]
    },
    {
      name: "Size",
      position: 0,
      visible: true,
      variation: true,
      options: [
        "S",
        "M"
      ]
    }
  ],
  default_attributes: [
    {
      id: 6,
      option: "Black"
    },
    {
      name: "Size",
      option: "S"
    }
  ]
}

woocommerce.post("products", data).parsed_response
```

> JSON response example:

```json
{
    "id": 2101,
    "name": "ATUM BOM Test",
    "slug": "atum-bom-test-2",
    "permalink": "https://example.com/product/atum-bom-test/",
    "date_created": "2019-11-06T12:44:23",
    "date_created_gmt": "2019-11-06T11:44:23",
    "date_modified": "2019-11-06T12:44:23",
    "date_modified_gmt": "2019-11-06T11:44:23",
    "type": "variable-product-part",
    "status": "publish",
    "featured": false,
    "catalog_visibility": "visible",
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
    "sku": "",
    "price": "",
    "regular_price": "",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "price_html": "",
    "on_sale": false,
    "purchasable": false,
    "total_sales": 0,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "external_url": "",
    "button_text": "",
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": false,
    "stock_quantity": null,
    "stock_status": "outofstock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "sold_individually": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_required": false,
    "shipping_taxable": false,
    "shipping_class": "",
    "shipping_class_id": 0,
    "reviews_allowed": true,
    "average_rating": "0",
    "rating_count": 0,
    "related_ids": [
        31,
        103,
        19,
        47,
        2096
    ],
    "upsell_ids": [],
    "cross_sell_ids": [],
    "parent_id": 0,
    "purchase_note": "",
    "categories": [
        {
            "id": 9,
            "name": "Clothing",
            "slug": "clothing"
        },
        {
            "id": 14,
            "name": "T-shirts",
            "slug": "t-shirts"
        }
    ],
    "tags": [],
    "images": [
        {
            "id": 2097,
            "date_created": "2019-11-06T13:44:21",
            "date_created_gmt": "2019-11-06T11:44:21",
            "date_modified": "2019-11-06T13:44:21",
            "date_modified_gmt": "2019-11-06T11:44:21",
            "src": "https://example.com/wp-content/uploads/2019/11/T_4_front-20.jpg",
            "name": "T_4_front-20.jpg",
            "alt": ""
        },
        {
            "id": 2098,
            "date_created": "2019-11-06T13:44:21",
            "date_created_gmt": "2019-11-06T11:44:21",
            "date_modified": "2019-11-06T13:44:21",
            "date_modified_gmt": "2019-11-06T11:44:21",
            "src": "https://example.com/wp-content/uploads/2019/11/T_4_back-20.jpg",
            "name": "T_4_back-20.jpg",
            "alt": ""
        },
        {
            "id": 2099,
            "date_created": "2019-11-06T13:44:22",
            "date_created_gmt": "2019-11-06T11:44:22",
            "date_modified": "2019-11-06T13:44:22",
            "date_modified_gmt": "2019-11-06T11:44:22",
            "src": "https://example.com/wp-content/uploads/2019/11/T_3_front-20.jpg",
            "name": "T_3_front-20.jpg",
            "alt": ""
        },
        {
            "id": 2100,
            "date_created": "2019-11-06T13:44:22",
            "date_created_gmt": "2019-11-06T11:44:22",
            "date_modified": "2019-11-06T13:44:22",
            "date_modified_gmt": "2019-11-06T11:44:22",
            "src": "https://example.com/wp-content/uploads/2019/11/T_3_back-20.jpg",
            "name": "T_3_back-20.jpg",
            "alt": ""
        }
    ],
    "attributes": [
        {
            "id": 0,
            "name": "Size",
            "position": 0,
            "visible": true,
            "variation": true,
            "options": [
                "S",
                "M"
            ]
        }
    ],
    "default_attributes": [
        {
            "id": 0,
            "name": "",
            "option": "black"
        },
        {
            "id": 0,
            "name": "Size",
            "option": "S"
        }
    ],
    "variations": [],
    "grouped_products": [],
    "menu_order": 0,
    "meta_data": [],
    "bundle_layout": "",
    "bundled_by": [],
    "bundled_items": [],
    "purchase_price": 0,
    "supplier_id": 0,
    "supplier_sku": "",
    "atum_controlled": false,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inheritable": false,
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
    "has_location": null,
    "update_date": "2019-11-06T10:44:23",
    "atum_locations": [],
    "linked_bom": [],
    "sync_purchase_price": false,
    "bom_sellable": false,
    "minimum_threshold": null,
    "available_to_purchase": null,
    "selling_priority": null,
    "calculated_stock": null,
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/2101"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products"
            }
        ]
    }
}
```

## Retrieve a product ##

This API lets you retrieve and view a specific product by ID.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products/70 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products/70")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products/70')); ?>
```

```python
print(wcapi.get("products/70").json())
```

```ruby
woocommerce.get("products/70").parsed_response
```

> JSON response example:

```json
{
    "id": 70,
    "name": "Flying Ninja",
    "slug": "flying-ninja",
    "permalink": "https://example.com/product/flying-ninja/",
    "date_created": "2013-06-07T13:25:01",
    "date_created_gmt": "2013-06-07T11:25:01",
    "date_modified": "2019-10-25T11:57:08",
    "date_modified_gmt": "2019-10-25T09:57:08",
    "type": "simple",
    "status": "publish",
    "featured": false,
    "catalog_visibility": "visible",
    "description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n",
    "short_description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n",
    "sku": "",
    "price": "50",
    "regular_price": "50",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "price_html": "",
    "on_sale": false,
    "purchasable": false,
    "total_sales": 54,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "external_url": "",
    "button_text": "",
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": true,
    "stock_quantity": 229,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "sold_individually": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_required": true,
    "shipping_taxable": true,
    "shipping_class": "",
    "shipping_class_id": 0,
    "reviews_allowed": true,
    "average_rating": "4.00",
    "rating_count": 4,
    "related_ids": [
        76,
        73,
        175,
        79,
        507
    ],
    "upsell_ids": [],
    "cross_sell_ids": [],
    "parent_id": 0,
    "purchase_note": "",
    "categories": [
        {
            "id": 12,
            "name": "Posters",
            "slug": "posters"
        }
    ],
    "tags": [],
    "images": [
        {
            "id": 71,
            "date_created": "2013-06-07T13:24:19",
            "date_created_gmt": "2013-06-07T11:24:19",
            "date_modified": "2013-06-07T13:24:19",
            "date_modified_gmt": "2013-06-07T11:24:19",
            "src": "https://example.com/wp-content/uploads/2013/06/poster_2_up.jpg",
            "name": "poster_2_up",
            "alt": ""
        },
        {
            "id": 72,
            "date_created": "2013-06-07T13:24:47",
            "date_created_gmt": "2013-06-07T11:24:47",
            "date_modified": "2013-06-07T13:24:47",
            "date_modified_gmt": "2013-06-07T11:24:47",
            "src": "https://example.com/wp-content/uploads/2013/06/Poster_2_flat.jpg",
            "name": "Poster_2_flat",
            "alt": ""
        }
    ],
    "attributes": [],
    "default_attributes": [],
    "variations": [],
    "grouped_products": [],
    "menu_order": 0,
    "meta_data": [],
    "bundle_layout": "",
    "bundled_by": [],
    "bundled_items": [],
    "purchase_price": 9,
    "supplier_id": 399,
    "supplier_sku": "",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inheritable": false,
    "inbound_stock": 1,
    "stock_on_hold": 48,
    "sold_today": 0,
    "sales_last_days": 0,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "has_location": true,
    "update_date": "2019-10-25T06:25:24",
    "atum_locations": [
        {
            "id": 39,
            "name": "Italy",
            "slug": "italy"
        },
        {
            "id": 50,
            "name": "Madrid",
            "slug": "madrid"
        },
        {
            "id": 37,
            "name": "Spain",
            "slug": "spain"
        },
        {
            "id": 38,
            "name": "United Kingdom",
            "slug": "united-kingdom"
        },
        {
            "id": 49,
            "name": "Valencia",
            "slug": "valencia"
        }
    ],
    "linked_bom": [
        {
            "bom_id": 183,
            "bom_type": "raw_material",
            "qty": 2
        }
    ],
    "sync_purchase_price": false,
    "calculated_stock": 229,
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/70"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products"
            }
        ]
    }
}
```

## List all products ##

This API helps you to view all the products.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/products</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/products \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("products")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('products')); ?>
```

```python
print(wcapi.get("products").json())
```

```ruby
woocommerce.get("products").parsed_response
```

> JSON response example:

```json
[
  {
      "id": 507,
      "name": "ABC 123 XPTO",
      "slug": "abc-123-xpto",
      "permalink": "https://example.com/product/abc-123-xpto/",
      "date_created": "2018-12-28T08:21:22",
      "date_created_gmt": "2018-12-28T07:21:22",
      "date_modified": "2019-10-22T13:34:08",
      "date_modified_gmt": "2019-10-22T11:34:08",
      "type": "simple",
      "status": "publish",
      "featured": false,
      "catalog_visibility": "visible",
      "description": "",
      "short_description": "",
      "sku": "",
      "price": null,
      "regular_price": null,
      "sale_price": "",
      "date_on_sale_from": null,
      "date_on_sale_from_gmt": null,
      "date_on_sale_to": null,
      "date_on_sale_to_gmt": null,
      "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>5,32</span> &ndash; <span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>20,00</span>",
      "on_sale": false,
      "purchasable": true,
      "total_sales": 58,
      "virtual": false,
      "downloadable": false,
      "downloads": [],
      "download_limit": -1,
      "download_expiry": -1,
      "external_url": "",
      "button_text": "",
      "tax_status": "taxable",
      "tax_class": "",
      "manage_stock": true,
      "stock_quantity": 0,
      "stock_status": "outofstock",
      "backorders": "no",
      "backorders_allowed": false,
      "backordered": false,
      "sold_individually": false,
      "weight": "",
      "dimensions": {
          "length": "",
          "width": "",
          "height": ""
      },
      "shipping_required": true,
      "shipping_taxable": true,
      "shipping_class": "",
      "shipping_class_id": 0,
      "reviews_allowed": true,
      "average_rating": "0.00",
      "rating_count": 0,
      "related_ids": [
          70,
          76,
          79,
          175,
          67
      ],
      "upsell_ids": [],
      "cross_sell_ids": [],
      "parent_id": 0,
      "purchase_note": "",
      "categories": [
          {
              "id": 12,
              "name": "Posters",
              "slug": "posters"
          }
      ],
      "tags": [],
      "images": [],
      "attributes": [],
      "default_attributes": [],
      "variations": [],
      "grouped_products": [],
      "menu_order": 0,
      "meta_data": [],
      "bundle_layout": "",
      "bundled_by": [],
      "bundled_items": [],
      "purchase_price": 2,
      "supplier_id": 399,
      "supplier_sku": "CRYPTO",
      "atum_controlled": true,
      "out_stock_date": "2019-09-26T07:06:23",
      "out_stock_threshold": 0,
      "inheritable": false,
      "inbound_stock": 6,
      "stock_on_hold": 39,
      "sold_today": 0,
      "sales_last_days": 2,
      "reserved_stock": 2,
      "customer_returns": 0,
      "warehouse_damage": 0,
      "lost_in_post": 3,
      "other_logs": 1,
      "out_stock_days": 34,
      "lost_sales": 0,
      "has_location": false,
      "update_date": null,
      "atum_locations": [],
      "linked_bom": [],
      "sync_purchase_price": false,
      "mi_inventories": [
          152,
          55,
          126
      ],
      "multi_inventory": "yes",
      "inventory_sorting_mode": "global",
      "inventory_iteration": "global",
      "expirable_inventories": "global",
      "price_per_inventory": "global",
      "selectable_inventories": "global",
      "selectable_inventories_mode": "global",
      "_links": {
          "self": [
              {
                  "href": "https://example.com/wp-json/wc/v3/products/507"
              }
          ],
          "collection": [
              {
                  "href": "https://example.com/wp-json/wc/v3/products"
              }
          ]
      }
  },
  {
      "id": 90,
      "name": "Woo Album #3",
      "slug": "woo-album-3",
      "permalink": "https://example.com/product/woo-album-3/",
      "date_created": "2013-06-07T13:35:18",
      "date_created_gmt": "2013-06-07T11:35:18",
      "date_modified": "2019-10-30T11:50:51",
      "date_modified_gmt": "2019-10-30T10:50:51",
      "type": "simple",
      "status": "publish",
      "featured": false,
      "catalog_visibility": "visible",
      "description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n<p>&nbsp;</p>\n<div class=\"atum-mi-no-info\">This product has no inventory info available.</div>\n",
      "short_description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n",
      "sku": "WOO3",
      "price": null,
      "regular_price": null,
      "sale_price": "",
      "date_on_sale_from": null,
      "date_on_sale_from_gmt": null,
      "date_on_sale_to": null,
      "date_on_sale_to_gmt": null,
      "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>10,00</span> &ndash; <span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>15,70</span>",
      "on_sale": false,
      "purchasable": true,
      "total_sales": 137,
      "virtual": false,
      "downloadable": true,
      "downloads": [],
      "download_limit": -1,
      "download_expiry": -1,
      "external_url": "",
      "button_text": "",
      "tax_status": "taxable",
      "tax_class": "",
      "manage_stock": true,
      "stock_quantity": 0,
      "stock_status": "outofstock",
      "backorders": "no",
      "backorders_allowed": false,
      "backordered": false,
      "sold_individually": false,
      "weight": "",
      "dimensions": {
          "length": "",
          "width": "",
          "height": ""
      },
      "shipping_required": true,
      "shipping_taxable": true,
      "shipping_class": "",
      "shipping_class_id": 0,
      "reviews_allowed": false,
      "average_rating": "3.00",
      "rating_count": 1,
      "related_ids": [
          99,
          96,
          669,
          83,
          649
      ],
      "upsell_ids": [],
      "cross_sell_ids": [],
      "parent_id": 0,
      "purchase_note": "",
      "categories": [
          {
              "id": 15,
              "name": "Albums",
              "slug": "albums"
          },
          {
              "id": 11,
              "name": "Music",
              "slug": "music"
          }
      ],
      "tags": [],
      "images": [
          {
              "id": 91,
              "date_created": "2013-06-07T13:34:58",
              "date_created_gmt": "2013-06-07T11:34:58",
              "date_modified": "2013-06-07T13:34:58",
              "date_modified_gmt": "2013-06-07T11:34:58",
              "src": "https://example.com/wp-content/uploads/2013/06/cd_3_angle.jpg",
              "name": "cd_3_angle",
              "alt": ""
          },
          {
              "id": 92,
              "date_created": "2013-06-07T13:35:10",
              "date_created_gmt": "2013-06-07T11:35:10",
              "date_modified": "2013-06-07T13:35:10",
              "date_modified_gmt": "2013-06-07T11:35:10",
              "src": "https://example.com/wp-content/uploads/2013/06/cd_3_flat.jpg",
              "name": "cd_3_flat",
              "alt": ""
          }
      ],
      "attributes": [],
      "default_attributes": [],
      "variations": [],
      "grouped_products": [],
      "menu_order": 0,
      "meta_data": [
          {
              "id": 1390,
              "key": "_download_type",
              "value": ""
          },
          {
              "id": 10290,
              "key": "_bom_stock_control",
              "value": "advanced"
          }
      ],
      "bundle_layout": "",
      "bundled_by": [],
      "bundled_items": [],
      "purchase_price": 6,
      "supplier_id": 399,
      "supplier_sku": "SUPSK1",
      "atum_controlled": true,
      "out_stock_date": "2019-10-25T10:32:12",
      "out_stock_threshold": 0,
      "inheritable": false,
      "inbound_stock": 5,
      "stock_on_hold": 39,
      "sold_today": 0,
      "sales_last_days": 0,
      "reserved_stock": 0,
      "customer_returns": 0,
      "warehouse_damage": 0,
      "lost_in_post": 0,
      "other_logs": 1,
      "out_stock_days": 4,
      "lost_sales": 0,
      "has_location": true,
      "update_date": null,
      "atum_locations": [
          {
              "id": 39,
              "name": "Italy",
              "slug": "italy"
          }
      ],
      "linked_bom": [
          {
              "bom_id": 175,
              "bom_type": "product_part",
              "qty": 3
          },
          {
              "bom_id": 182,
              "bom_type": "raw_material",
              "qty": 9
          },
          {
              "bom_id": 184,
              "bom_type": "product_part",
              "qty": 35
          }
      ],
      "sync_purchase_price": true,
      "calculated_stock": 0,
      "mi_inventories": [
          1,
          2,
          5,
          85,
          3
      ],
      "multi_inventory": "yes",
      "inventory_sorting_mode": "global",
      "inventory_iteration": "global",
      "expirable_inventories": "global",
      "price_per_inventory": "global",
      "selectable_inventories": "global",
      "selectable_inventories_mode": "global",
      "_links": {
          "self": [
              {
                  "href": "https://example.com/wp-json/wc/v3/products/90"
              }
          ],
          "collection": [
              {
                  "href": "https://example.com/wp-json/wc/v3/products"
              }
          ]
      }
  }
]
```

#### Available parameters ####

| Parameter                     | Type    | Description                                                                                                                                                                                                       |
|-------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`                     | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                                      |
| `page`                        | integer | Current page of the collection. Default is `1`.                                                                                                                                                                   |
| `per_page`                    | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                                            |
| `search`                      | string  | Limit results to those matching a string.                                                                                                                                                                         |
| `after`                       | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                                       |
| `before`                      | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                                      |
| `modified_after`              | string  | Limit response to resources modified after a given ISO8601 compliant date.                                                                                                                                        |
| `modified_before`             | string  | Limit response to resources modified before a given ISO8601 compliant date.                                                                                                                                       |
| `exclude`                     | array   | Ensure result set excludes specific IDs.                                                                                                                                                                          |
| `include`                     | array   | Limit result set to specific ids.                                                                                                                                                                                 |
| `offset`                      | integer | Offset the result set by a specific number of items.                                                                                                                                                              |
| `order`                       | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                                       |
| `orderby`                     | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                                     |
| `parent`                      | array   | Limit result set to those of particular parent IDs.                                                                                                                                                               |
| `parent_exclude`              | array   | Limit result set to all items except those of a particular parent ID.                                                                                                                                             |
| `slug`                        | string  | Limit result set to products with a specific slug.                                                                                                                                                                |
| `status`                      | string  | Limit result set to products assigned a specific status. Options: `any`, `draft`, `pending`, `private` and `publish`. Default is `any`.                                                                           |
| `type`                        | string  | Limit result set to products assigned a specific type. Options: `simple`, `grouped`, `external`, `variable`, `product-part`, `raw-material`, `variable-product-part` and `variable-raw-material`.                 |
| `sku`                         | string  | Limit result set to products with a specific SKU.                                                                                                                                                                 |
| `featured`                    | boolean | Limit result set to featured products.                                                                                                                                                                            |
| `category`                    | string  | Limit result set to products assigned a specific category ID.                                                                                                                                                     |
| `tag`                         | string  | Limit result set to products assigned a specific tag ID.                                                                                                                                                          |
| `shipping_class`              | string  | Limit result set to products assigned a specific shipping class ID.                                                                                                                                               |
| `attribute`                   | string  | Limit result set to products with a specific attribute.                                                                                                                                                           |
| `attribute_term`              | string  | Limit result set to products with a specific attribute term ID (required an assigned attribute).                                                                                                                  |
| `tax_class`                   | string  | Limit result set to products with a specific tax class. Default options: `standard`, `reduced-rate` and `zero-rate`.                                                                                              |
| `on_sale`                     | boolean | Limit result set to products on sale.                                                                                                                                                                             |
| `min_price`                   | string  | Limit result set to products based on a minimum price.                                                                                                                                                            |
| `max_price`                   | string  | Limit result set to products based on a maximum price.                                                                                                                                                            |
| `stock_status`                | string  | Limit result set to products with specified stock status. Options: `instock`, `outofstock` and `onbackorder`.                                                                                                     |
| `atum_location`               | string  | Limit result set to products assigned a specific ATUM Location ID. <i class="label label-atum">ATUM</i>                                                                                                           |
| `atum_controlled`             | boolean | Limit result set to products controlled by ATUM. <i class="label label-atum">ATUM</i>                                                                                                                             |
| `min_purchase_price`          | number  | Limit result set to products based on a minimum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `max_purchase_price`          | number  | Limit result set to products based on a maximum purchase price. <i class="label label-atum">ATUM</i>                                                                                                              |
| `supplier`                    | integer | Limit result set to products linked to the specified Supplier ID. <i class="label label-atum">ATUM</i>                                                                                                            |
| `supplier_sku`                | integer | Limit result set to products with a specific Supplier SKU. <i class="label label-atum">ATUM</i>                                                                                                                   |
| `multi_inventory`             | string  | Limit result set to products with a specific Multi-Inventory status. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                     |
| `inventory_sorting_mode`      | string  | Limit result set to products with a specific inventory sorting mode. Options: `fifo`, `lifo`, `bbe`, `manual` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i> |
| `inventory_iteration`         | string  | Limit result set to products with a specific inventory iteration. Options: `use_next`, `out_of_stock` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>         |
| `expirable_inventories`       | string  | Limit result set to products with a specific expirable inventories option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>               |
| `price_per_inventory`         | string  | Limit result set to products with a specific price per inventory option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>                 |
| `selectable_inventories`      | string  | Limit result set to products with a specific selectable inventories option. Options: `yes`, `no` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>              |
| `selectable_inventories_mode` | string  | Limit result set to products with a specific selectable inventories mode option. Options: `dropdown`, `list` and `global`. <i class="label label-addon">Multi-Inventory</i> <i class="label label-atum">ATUM</i>  |
| `bom_sellable`                | boolean | Limit result set to sellable BOM products. It should be used in conjunction with the `type` set to any BOM type. <i class="label label-addon">Product Levels</i> <i class="label label-atum">ATUM</i>             |

## Update a product ##

This API lets you make changes to a product.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/products/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/products/70 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "purchase_price": 24.54
}'
```

```javascript
const data = {
  purchase_price: 24.54
};

WooCommerce.put("products/70", data)
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
    'purchase_price' => 24.54
];

print_r($woocommerce->put('products/70', $data));
?>
```

```python
data = {
    "purchase_price": 24.54
}

print(wcapi.put("products/70", data).json())
```

```ruby
data = {
  purchase_price: 24.54
}

woocommerce.put("products/70", data).parsed_response
```

> JSON response example:

```json
{
    "id": 70,
    "name": "Flying Ninja",
    "slug": "flying-ninja",
    "permalink": "https://example.com/product/flying-ninja/",
    "date_created": "2013-06-07T13:25:01",
    "date_created_gmt": "2013-06-07T11:25:01",
    "date_modified": "2019-11-07T12:54:35",
    "date_modified_gmt": "2019-11-07T11:54:35",
    "type": "simple",
    "status": "publish",
    "featured": false,
    "catalog_visibility": "visible",
    "description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n",
    "short_description": "<p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.</p>\n",
    "sku": "",
    "price": "50",
    "regular_price": "50",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>50,00</span>",
    "on_sale": false,
    "purchasable": true,
    "total_sales": 54,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "external_url": "",
    "button_text": "",
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": true,
    "stock_quantity": 229,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "sold_individually": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_required": true,
    "shipping_taxable": true,
    "shipping_class": "",
    "shipping_class_id": 0,
    "reviews_allowed": true,
    "average_rating": "4.00",
    "rating_count": 4,
    "related_ids": [
        507,
        76,
        73,
        175,
        67
    ],
    "upsell_ids": [],
    "cross_sell_ids": [],
    "parent_id": 0,
    "purchase_note": "",
    "categories": [
        {
            "id": 12,
            "name": "Posters",
            "slug": "posters"
        }
    ],
    "tags": [],
    "images": [
        {
            "id": 71,
            "date_created": "2013-06-07T13:24:19",
            "date_created_gmt": "2013-06-07T11:24:19",
            "date_modified": "2013-06-07T13:24:19",
            "date_modified_gmt": "2013-06-07T11:24:19",
            "src": "https://example.com/wp-content/uploads/2013/06/poster_2_up.jpg",
            "name": "poster_2_up",
            "alt": ""
        },
        {
            "id": 72,
            "date_created": "2013-06-07T13:24:47",
            "date_created_gmt": "2013-06-07T11:24:47",
            "date_modified": "2013-06-07T13:24:47",
            "date_modified_gmt": "2013-06-07T11:24:47",
            "src": "https://example.com/wp-content/uploads/2013/06/Poster_2_flat.jpg",
            "name": "Poster_2_flat",
            "alt": ""
        }
    ],
    "attributes": [],
    "default_attributes": [],
    "variations": [],
    "grouped_products": [],
    "menu_order": 0,
    "meta_data": [],
    "bundle_layout": "",
    "bundled_by": [],
    "bundled_items": [],
    "purchase_price": 24.54,
    "supplier_id": 399,
    "supplier_sku": "",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inheritable": false,
    "inbound_stock": 1,
    "stock_on_hold": 48,
    "sold_today": 0,
    "sales_last_days": 0,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "has_location": true,
    "update_date": "2019-11-07T10:54:37",
    "atum_locations": [
        {
            "id": 39,
            "name": "Italy",
            "slug": "italy"
        },
        {
            "id": 50,
            "name": "Madrid",
            "slug": "madrid"
        },
        {
            "id": 37,
            "name": "Spain",
            "slug": "spain"
        },
        {
            "id": 38,
            "name": "United Kingdom",
            "slug": "united-kingdom"
        },
        {
            "id": 49,
            "name": "Valencia",
            "slug": "valencia"
        }
    ],
    "linked_bom": [
        {
            "bom_id": 183,
            "bom_type": "raw_material",
            "qty": 2
        }
    ],
    "sync_purchase_price": false,
    "calculated_stock": 229,
    "mi_inventories": [
        62
    ],
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/70"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products"
            }
        ]
    }
}
```

## Delete a product ##

This API helps you delete a product.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/products/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/products/1998?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("products/1998", {
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
<?php print_r($woocommerce->delete('products/1998', ['force' => true])); ?>
```

```python
print(wcapi.delete("products/1998", params={"force": True}).json())
```

```ruby
woocommerce.delete("products/1998", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 1998,
    "name": "ATUM Test Product",
    "slug": "atum-test-product",
    "permalink": "https://example.com/product/atum-test-product/",
    "date_created": "2019-11-06T08:54:04",
    "date_created_gmt": "2019-11-06T07:54:04",
    "date_modified": "2019-11-07T13:00:07",
    "date_modified_gmt": "2019-11-07T12:00:07",
    "type": "simple",
    "status": "publish",
    "featured": false,
    "catalog_visibility": "visible",
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
    "sku": "",
    "price": "21.99",
    "regular_price": "21.99",
    "sale_price": "",
    "date_on_sale_from": null,
    "date_on_sale_from_gmt": null,
    "date_on_sale_to": null,
    "date_on_sale_to_gmt": null,
    "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>21,99</span>",
    "on_sale": false,
    "purchasable": true,
    "total_sales": 0,
    "virtual": false,
    "downloadable": false,
    "downloads": [],
    "download_limit": -1,
    "download_expiry": -1,
    "external_url": "",
    "button_text": "",
    "tax_status": "taxable",
    "tax_class": "",
    "manage_stock": false,
    "stock_quantity": null,
    "stock_status": "instock",
    "backorders": "no",
    "backorders_allowed": false,
    "backordered": false,
    "sold_individually": false,
    "weight": "",
    "dimensions": {
        "length": "",
        "width": "",
        "height": ""
    },
    "shipping_required": true,
    "shipping_taxable": true,
    "shipping_class": "",
    "shipping_class_id": 0,
    "reviews_allowed": true,
    "average_rating": "0",
    "rating_count": 0,
    "related_ids": [
        34,
        50,
        37,
        115,
        103
    ],
    "upsell_ids": [],
    "cross_sell_ids": [],
    "parent_id": 0,
    "purchase_note": "",
    "categories": [
        {
            "id": 9,
            "name": "Clothing",
            "slug": "clothing"
        },
        {
            "id": 14,
            "name": "T-shirts",
            "slug": "t-shirts"
        }
    ],
    "tags": [],
    "images": [
        {
            "id": 1996,
            "date_created": "2019-11-06T09:54:03",
            "date_created_gmt": "2019-11-06T07:54:03",
            "date_modified": "2019-11-06T09:54:03",
            "date_modified_gmt": "2019-11-06T07:54:03",
            "src": "https://example.com/wp-content/uploads/2019/11/T_2_front-8.jpg",
            "name": "T_2_front-8.jpg",
            "alt": ""
        },
        {
            "id": 1997,
            "date_created": "2019-11-06T09:54:04",
            "date_created_gmt": "2019-11-06T07:54:04",
            "date_modified": "2019-11-06T09:54:04",
            "date_modified_gmt": "2019-11-06T07:54:04",
            "src": "https://example.com/wp-content/uploads/2019/11/T_2_back-8.jpg",
            "name": "T_2_back-8.jpg",
            "alt": ""
        }
    ],
    "attributes": [],
    "default_attributes": [],
    "variations": [],
    "grouped_products": [],
    "menu_order": 0,
    "meta_data": [],
    "bundle_layout": "",
    "bundled_by": [],
    "bundled_items": [],
    "purchase_price": 15.2,
    "supplier_id": 399,
    "supplier_sku": "TEST1",
    "atum_controlled": true,
    "out_stock_date": null,
    "out_stock_threshold": 0,
    "inheritable": false,
    "inbound_stock": 0,
    "stock_on_hold": 0,
    "sold_today": 0,
    "sales_last_days": 0,
    "reserved_stock": 0,
    "customer_returns": 0,
    "warehouse_damage": 0,
    "lost_in_post": 0,
    "other_logs": 0,
    "out_stock_days": 0,
    "lost_sales": 0,
    "has_location": true,
    "update_date": "2019-11-07T07:40:51",
    "atum_locations": [
        {
            "id": 39,
            "name": "Italy",
            "slug": "italy"
        },
        {
            "id": 37,
            "name": "Spain",
            "slug": "spain"
        }
    ],
    "linked_bom": [
        {
            "bom_id": 175,
            "bom_type": "product_part",
            "qty": 3
        }
    ],
    "sync_purchase_price": false,
    "calculated_stock": 117,
    "mi_inventories": [
        174
    ],
    "multi_inventory": "global",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/products/1998"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/products"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                               |
|-----------|--------|---------------------------------------------------------------------------|
| `force`   | string | Use `true` whether to permanently delete the product, Default is `false`. |

## Batch update products ##

This API helps you to batch create, update and delete multiple products.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/products/batch</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/products/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "create": [
    {
      "name": "TEST Batch Product",
      "type": "simple",
      "regular_price": "21.99",
      "virtual": true,
      "downloadable": true,
      "downloads": [
        {
          "name": "Woo Single",
          "file": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
        }
      ],
      "categories": [
        {
          "id": 11
        },
        {
          "id": 13
        }
      ],
      "images": [
        {
          "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
        }
      ]
    },
    {
      "name": "TEST Batch BOM Product",
      "type": "raw-material",
      "regular_price": "21.99",
      "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
      "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
      "categories": [
        {
          "id": 9
        },
        {
          "id": 14
        }
      ],
      "images": [
        {
          "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
        },
        {
          "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
        }
      ]
    }
  ],
  "update": [
    {
      "id": 507,
      "linked_bom": [
        {
          "bom_id": 183,
          "bom_type": "raw_material",
          "qty": 2
        },
        {
          "bom_id": 184,
          "bom_type": "product_part",
          "qty": 1
        }
      ],
      "multi_inventory": "no"
    }
  ],
  "delete": [
    2121
  ]
}'
```

```javascript
const data = {
   create: [
     {
       name: "TEST Batch Product",
       type: "simple",
       regular_price: "21.99",
       virtual: true,
       downloadable: true,
       downloads: [
         {
           name: "Woo Single",
           file: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
         }
       ],
       categories: [
         {
           id: 11
         },
         {
           id: 13
         }
       ],
       images: [
         {
           src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
         }
       ]
     },
     {
       name: "TEST Batch BOM Product",
       type: "raw-material",
       regular_price: "21.99",
       description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
       short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
       categories: [
         {
           id: 9
         },
         {
           id: 14
         }
       ],
       images: [
         {
           src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
         },
         {
           src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
         }
       ]
     }
   ],
   update: [
     {
       id: 507,
       linked_bom: [
         {
           bom_id: 183,
           bom_type: "raw_material",
           qty: 2
         },
         {
           bom_id: 184,
           bom_type: "product_part",
           qty: 1
         }
       ],
       multi_inventory: "no"
     }
   ],
   delete: [
     2121
   ]
};

WooCommerce.post("products/batch", data)
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
      'name' => 'TEST Batch Product',
      'type' => 'simple',
      'regular_price' => '21.99',
      'virtual' => true,
      'downloadable' => true,
      'downloads' => [
        [
          'name' => 'Woo Single',
          'file' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg'
        ]
      ],
      'categories' => [
        [
          'id' => 11
        ],
        [
          'id' => 13
        ]
      ],
      'images' => [
        [
          'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg'
        ]
      ]
    ],
    [
      'name' => 'TEST Batch BOM Product',
      'type' => 'raw-material',
      'regular_price' => '21.99',
      'description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.',
      'short_description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.',
      'categories' => [
        [
          'id' => 9
        ],
        [
          'id' => 14
        ]
      ],
      'images' => [
       [
          'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg'
        ],
        [
          'src' => 'http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg'
        ]
      ]
    ]
  ],
  'update' => [
    [
      'id' => 507,
      'linked_bom' => [
        [
          'bom_id' => 183,
          'bom_type' => 'raw_material',
          'qty' => 2
        ],
        [
          'bom_id' => 184,
          'bom_type' => 'product_part',
          'qty' => 1
        ]
      ],
      'multi_inventory' => 'no'
    ]
  ],
  'delete' => [
    2121
  ]
];

print_r($woocommerce->post('products/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "name": "TEST Batch Product",
     "type": "simple",
     "regular_price": "21.99",
     "virtual": true,
     "downloadable": true,
     "downloads": [
       {
         "name": "Woo Single",
         "file": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
       }
     ],
     "categories": [
       {
         "id": 11
       },
       {
         "id": 13
       }
     ],
     "images": [
       {
         "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
       }
     ]
   },
   {
     "name": "TEST Batch BOM Product",
     "type": "raw-material",
     "regular_price": "21.99",
     "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
     "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
     "categories": [
       {
         "id": 9
       },
       {
         "id": 14
       }
     ],
     "images": [
       {
         "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
       },
       {
         "src": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
       }
     ]
   }
 ],
 "update": [
   {
     "id": 507,
     "linked_bom": [
       {
         "bom_id": 183,
         "bom_type": "raw_material",
         "qty": 2
       },
       {
         "bom_id": 184,
         "bom_type": "product_part",
         "qty": 1
       }
     ],
     "multi_inventory": "no"
   }
 ],
 "delete": [
   2121
 ]
}

print(wcapi.post("products/batch", data).json())
```

```ruby
data = {
 create: [
   {
     name: "TEST Batch Product",
     type: "simple",
     regular_price: "21.99",
     virtual: true,
     downloadable: true,
     downloads: [
       {
         name: "Woo Single",
         file: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
       }
     ],
     categories: [
       {
         id: 11
       },
       {
         id: 13
       }
     ],
     images: [
       {
         src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
       }
     ]
   },
   {
     name: "TEST Batch BOM Product",
     type: "raw-material",
     regular_price: "21.99",
     description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
     short_description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
     categories: [
       {
         id: 9
       },
       {
         id: 14
       }
     ],
     images: [
       {
         src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_front.jpg"
       },
       {
         src: "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/T_2_back.jpg"
       }
     ]
   }
 ],
 update: [
   {
     id: 507,
     linked_bom: [
       {
         bom_id: 183,
         bom_type: "raw_material",
         qty: 2
       },
       {
         bom_id: 184,
         bom_type: "product_part",
         qty: 1
       }
     ],
     multi_inventory: "no"
   }
 ],
 delete: [
   2121
 ]
}

woocommerce.post("products/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2123,
            "name": "TEST Batch Product",
            "slug": "test-batch-product",
            "permalink": "https://example.com/product/test-batch-product/",
            "date_created": "2019-11-07T13:16:32",
            "date_created_gmt": "2019-11-07T12:16:32",
            "date_modified": "2019-11-07T13:16:32",
            "date_modified_gmt": "2019-11-07T12:16:32",
            "type": "simple",
            "status": "publish",
            "featured": false,
            "catalog_visibility": "visible",
            "description": "",
            "short_description": "",
            "sku": "",
            "price": "21.99",
            "regular_price": "21.99",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>21,99</span>",
            "on_sale": false,
            "purchasable": true,
            "total_sales": 0,
            "virtual": true,
            "downloadable": true,
            "downloads": [
                {
                    "id": "0e47b414-0469-4c6a-9ded-f2a8ea0b6ca4",
                    "name": "Woo Single",
                    "file": "http://demo.woothemes.com/woocommerce/wp-content/uploads/sites/56/2013/06/cd_4_angle.jpg"
                }
            ],
            "download_limit": -1,
            "download_expiry": -1,
            "external_url": "",
            "button_text": "",
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": false,
            "stock_quantity": null,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "sold_individually": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_required": false,
            "shipping_taxable": false,
            "shipping_class": "",
            "shipping_class_id": 0,
            "reviews_allowed": true,
            "average_rating": "0",
            "rating_count": 0,
            "related_ids": [
                649,
                83,
                90,
                87,
                96
            ],
            "upsell_ids": [],
            "cross_sell_ids": [],
            "parent_id": 0,
            "purchase_note": "",
            "categories": [
                {
                    "id": 11,
                    "name": "Music",
                    "slug": "music"
                },
                {
                    "id": 13,
                    "name": "Singles",
                    "slug": "singles"
                }
            ],
            "tags": [],
            "images": [
                {
                    "id": 2122,
                    "date_created": "2019-11-07T14:16:31",
                    "date_created_gmt": "2019-11-07T12:16:31",
                    "date_modified": "2019-11-07T14:16:31",
                    "date_modified_gmt": "2019-11-07T12:16:31",
                    "src": "https://example.com/wp-content/uploads/2019/11/cd_4_angle-1.jpg",
                    "name": "cd_4_angle-1.jpg",
                    "alt": ""
                }
            ],
            "attributes": [],
            "default_attributes": [],
            "variations": [],
            "grouped_products": [],
            "menu_order": 0,
            "meta_data": [],
            "bundle_layout": "",
            "bundled_by": [],
            "bundled_items": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "atum_controlled": false,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inheritable": false,
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
            "has_location": null,
            "update_date": "2019-11-07T11:16:32",
            "atum_locations": [],
            "linked_bom": [],
            "sync_purchase_price": false,
            "mi_inventories": [],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/2123"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products"
                    }
                ]
            }
        },
        {
            "id": 2126,
            "name": "TEST Batch BOM Product",
            "slug": "test-batch-bom-product",
            "permalink": "https://example.com/product/test-batch-bom-product/",
            "date_created": "2019-11-07T13:16:34",
            "date_created_gmt": "2019-11-07T12:16:34",
            "date_modified": "2019-11-07T13:16:34",
            "date_modified_gmt": "2019-11-07T12:16:34",
            "type": "raw-material",
            "status": "publish",
            "featured": false,
            "catalog_visibility": "visible",
            "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
            "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
            "sku": "",
            "price": "21.99",
            "regular_price": "21.99",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>21,99</span>",
            "on_sale": false,
            "purchasable": false,
            "total_sales": 0,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "external_url": "",
            "button_text": "",
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": true,
            "stock_quantity": null,
            "stock_status": "outofstock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "sold_individually": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_required": false,
            "shipping_taxable": false,
            "shipping_class": "",
            "shipping_class_id": 0,
            "reviews_allowed": true,
            "average_rating": "0",
            "rating_count": 0,
            "related_ids": [
                31,
                103,
                19,
                56,
                115
            ],
            "upsell_ids": [],
            "cross_sell_ids": [],
            "parent_id": 0,
            "purchase_note": "",
            "categories": [
                {
                    "id": 9,
                    "name": "Clothing",
                    "slug": "clothing"
                },
                {
                    "id": 14,
                    "name": "T-shirts",
                    "slug": "t-shirts"
                }
            ],
            "tags": [],
            "images": [
                {
                    "id": 2124,
                    "date_created": "2019-11-07T14:16:33",
                    "date_created_gmt": "2019-11-07T12:16:33",
                    "date_modified": "2019-11-07T14:16:33",
                    "date_modified_gmt": "2019-11-07T12:16:33",
                    "src": "https://example.com/wp-content/uploads/2019/11/T_2_front-12.jpg",
                    "name": "T_2_front-12.jpg",
                    "alt": ""
                },
                {
                    "id": 2125,
                    "date_created": "2019-11-07T14:16:33",
                    "date_created_gmt": "2019-11-07T12:16:33",
                    "date_modified": "2019-11-07T14:16:33",
                    "date_modified_gmt": "2019-11-07T12:16:33",
                    "src": "https://example.com/wp-content/uploads/2019/11/T_2_back-12.jpg",
                    "name": "T_2_back-12.jpg",
                    "alt": ""
                }
            ],
            "attributes": [],
            "default_attributes": [],
            "variations": [],
            "grouped_products": [],
            "menu_order": 0,
            "meta_data": [],
            "bundle_layout": "",
            "bundled_by": [],
            "bundled_items": [],
            "purchase_price": 0,
            "supplier_id": 0,
            "supplier_sku": "",
            "atum_controlled": false,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inheritable": false,
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
            "has_location": null,
            "update_date": "2019-11-07T11:16:34",
            "atum_locations": [],
            "linked_bom": [],
            "sync_purchase_price": false,
            "bom_sellable": null,
            "minimum_threshold": null,
            "available_to_purchase": null,
            "selling_priority": null,
            "calculated_stock": null,
            "mi_inventories": [],
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/2126"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 507,
            "name": "ABC 123 XPTO",
            "slug": "abc-123-xpto",
            "permalink": "https://example.com/product/abc-123-xpto/",
            "date_created": "2018-12-28T08:21:22",
            "date_created_gmt": "2018-12-28T07:21:22",
            "date_modified": "2019-11-07T13:16:35",
            "date_modified_gmt": "2019-11-07T12:16:35",
            "type": "simple",
            "status": "publish",
            "featured": false,
            "catalog_visibility": "visible",
            "description": "",
            "short_description": "",
            "sku": "",
            "price": "5.32",
            "regular_price": "5.32",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>5,32</span> &ndash; <span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>20,00</span>",
            "on_sale": false,
            "purchasable": true,
            "total_sales": 58,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "external_url": "",
            "button_text": "",
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": true,
            "stock_quantity": null,
            "stock_status": "outofstock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "sold_individually": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_required": true,
            "shipping_taxable": true,
            "shipping_class": "",
            "shipping_class_id": 0,
            "reviews_allowed": true,
            "average_rating": "0",
            "rating_count": 0,
            "related_ids": [
                79,
                70,
                73,
                175,
                76
            ],
            "upsell_ids": [],
            "cross_sell_ids": [],
            "parent_id": 0,
            "purchase_note": "",
            "categories": [
                {
                    "id": 12,
                    "name": "Posters",
                    "slug": "posters"
                }
            ],
            "tags": [],
            "images": [],
            "attributes": [],
            "default_attributes": [],
            "variations": [],
            "grouped_products": [],
            "menu_order": 0,
            "meta_data": [],
            "bundle_layout": "",
            "bundled_by": [],
            "bundled_items": [],
            "purchase_price": 2,
            "supplier_id": 399,
            "supplier_sku": "CRYPTO",
            "atum_controlled": true,
            "out_stock_date": "2019-09-26T07:06:23",
            "out_stock_threshold": 0,
            "inheritable": false,
            "inbound_stock": 6,
            "stock_on_hold": 39,
            "sold_today": 0,
            "sales_last_days": 2,
            "reserved_stock": 2,
            "customer_returns": 0,
            "warehouse_damage": 0,
            "lost_in_post": 3,
            "other_logs": 1,
            "out_stock_days": 34,
            "lost_sales": 0,
            "has_location": false,
            "update_date": "2019-11-07T08:40:50",
            "atum_locations": [],
            "linked_bom": [
                {
                    "bom_id": 183,
                    "bom_type": "raw_material",
                    "qty": 2
                },
                {
                    "bom_id": 184,
                    "bom_type": "product_part",
                    "qty": 1
                }
            ],
            "sync_purchase_price": false,
            "mi_inventories": [
                152,
                55,
                126
            ],
            "multi_inventory": "no",
            "inventory_sorting_mode": "global",
            "inventory_iteration": "use_next",
            "expirable_inventories": "no",
            "price_per_inventory": "yes",
            "selectable_inventories": "global",
            "selectable_inventories_mode": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/507"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 2121,
            "name": "ATUM Test Product",
            "slug": "atum-test-product",
            "permalink": "https://example.com/product/atum-test-product/",
            "date_created": "2019-11-07T13:11:59",
            "date_created_gmt": "2019-11-07T12:11:59",
            "date_modified": "2019-11-07T13:12:29",
            "date_modified_gmt": "2019-11-07T12:12:29",
            "type": "simple",
            "status": "publish",
            "featured": false,
            "catalog_visibility": "visible",
            "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
            "short_description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.",
            "sku": "",
            "price": "21.99",
            "regular_price": "21.99",
            "sale_price": "",
            "date_on_sale_from": null,
            "date_on_sale_from_gmt": null,
            "date_on_sale_to": null,
            "date_on_sale_to_gmt": null,
            "price_html": "<span class=\"woocommerce-Price-amount amount\"><span class=\"woocommerce-Price-currencySymbol\">&euro;</span>21,99</span>",
            "on_sale": false,
            "purchasable": true,
            "total_sales": 0,
            "virtual": false,
            "downloadable": false,
            "downloads": [],
            "download_limit": -1,
            "download_expiry": -1,
            "external_url": "",
            "button_text": "",
            "tax_status": "taxable",
            "tax_class": "",
            "manage_stock": false,
            "stock_quantity": null,
            "stock_status": "instock",
            "backorders": "no",
            "backorders_allowed": false,
            "backordered": false,
            "sold_individually": false,
            "weight": "",
            "dimensions": {
                "length": "",
                "width": "",
                "height": ""
            },
            "shipping_required": true,
            "shipping_taxable": true,
            "shipping_class": "",
            "shipping_class_id": 0,
            "reviews_allowed": true,
            "average_rating": "0",
            "rating_count": 0,
            "related_ids": [
                50,
                15,
                19,
                31,
                40
            ],
            "upsell_ids": [],
            "cross_sell_ids": [],
            "parent_id": 0,
            "purchase_note": "",
            "categories": [
                {
                    "id": 9,
                    "name": "Clothing",
                    "slug": "clothing"
                },
                {
                    "id": 14,
                    "name": "T-shirts",
                    "slug": "t-shirts"
                }
            ],
            "tags": [],
            "images": [
                {
                    "id": 2119,
                    "date_created": "2019-11-07T14:11:58",
                    "date_created_gmt": "2019-11-07T12:11:58",
                    "date_modified": "2019-11-07T14:11:58",
                    "date_modified_gmt": "2019-11-07T12:11:58",
                    "src": "https://example.com/wp-content/uploads/2019/11/T_2_front-11.jpg",
                    "name": "T_2_front-11.jpg",
                    "alt": ""
                },
                {
                    "id": 2120,
                    "date_created": "2019-11-07T14:11:58",
                    "date_created_gmt": "2019-11-07T12:11:58",
                    "date_modified": "2019-11-07T14:11:58",
                    "date_modified_gmt": "2019-11-07T12:11:58",
                    "src": "https://example.com/wp-content/uploads/2019/11/T_2_back-11.jpg",
                    "name": "T_2_back-11.jpg",
                    "alt": ""
                }
            ],
            "attributes": [],
            "default_attributes": [],
            "variations": [],
            "grouped_products": [],
            "menu_order": 0,
            "meta_data": [],
            "bundle_layout": "",
            "bundled_by": [],
            "bundled_items": [],
            "purchase_price": 15.2,
            "supplier_id": 399,
            "supplier_sku": "TEST1",
            "atum_controlled": true,
            "out_stock_date": null,
            "out_stock_threshold": 0,
            "inheritable": false,
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
            "has_location": null,
            "update_date": "2019-11-07T11:12:29",
            "atum_locations": [
                {
                    "id": 39,
                    "name": "Italy",
                    "slug": "italy"
                },
                {
                    "id": 37,
                    "name": "Spain",
                    "slug": "spain"
                }
            ],
            "linked_bom": [
                {
                    "bom_id": 175,
                    "bom_type": "product_part",
                    "qty": 3
                }
            ],
            "sync_purchase_price": false,
            "calculated_stock": 117,
            "mi_inventories": [
                180
            ],
            "multi_inventory": "global",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products/2121"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/products"
                    }
                ]
            }
        }
    ]
}
```
