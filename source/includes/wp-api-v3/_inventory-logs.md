# Inventory logs #

The inventory logs API allows you to create, view, update, and delete individual, or a batch, of inventory logs.

## Inventory log properties ##

| Attribute            | Type      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|----------------------|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                 | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `status`             | string    | Inventory log status. Options: `atum_pending`, `atum_completed` and `trash`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `currency`           | string    | Currency the inventory log was created with, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`. Default is `USD`. |
| `date_created`       | date-time | The date the inventory log was created, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `date_created_gmt`   | date-time | The date the inventory log was created, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `date_modified`      | date-time | The date the inventory log was last modified, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `date_modified_gmt`  | date-time | The date the inventory log was last modified, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `discount_total`     | string    | Total discount amount for the inventory log. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `discount_tax`       | string    | Total discount tax amount for the inventory log. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `shipping_total`     | string    | Total shipping amount for the inventory log. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `shipping_tax`       | string    | Total shipping tax amount for the inventory log. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `cart_tax`           | string    | Sum of line item taxes only. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `total`              | string    | Grand total. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `total_tax`          | string    | Sum of all taxes. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `prices_include_tax` | boolean   | True the prices included tax during checkout. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `date_completed`     | date-time | The date the inventory log was completed, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `date_completed_gmt` | date-time | The date the inventory log was completed, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `type`               | string    | The log type. Options: `reserved-stock`, `customer-returns`, `warehouse-damage`, `lost-in-post`, `other`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `order`              | integer   | The WooCommerce's order ID to which this Log is linked to.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `reservation_date`   | date-time | The date for when the stock is reserved. Only for IL with type `reserved-stock`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `return_date`        | date-time | The date for when the customer returned the stock. Only for IL with type `customer-returns`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `damage_date`        | date-time | The date for when the stock was damaged at warehouse. Only for IL with type `warehouse-damage`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `shipping_company`   | string    | The name of the company that lost in post. Only for IL with type `lost-in-post`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `custom_name`        | string    | The custom name for the 'other' log types. Only for IL with type `other`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `meta_data`          | array     | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `line_items`         | array     | Line items data. See [Inventory Log - Line items properties](#inventory-log-line-items-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `tax_lines`          | array     | Tax lines data. See [Inventory Log - Tax lines properties](#inventory-log-tax-lines-properties) <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `shipping_lines`     | array     | Shipping lines data. See [Inventory Log - Shipping lines properties](#inventory-log-shipping-lines-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `fee_lines`          | array     | Fee lines data. See [Inventory Log - Fee lines properties](#inventory-log-fee-lines-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `meta_data`          | array     | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `description`        | string    | The inventory log description.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Inventory Log - Meta data properties ###

| Attribute | Type    | Description                                        |
|-----------|---------|----------------------------------------------------|
| `id`      | integer | Meta ID. <i class="label label-info">read-only</i> |
| `key`     | string  | Meta key.                                          |
| `value`   | string  | Meta value.                                        |

### Inventory Log - Line items properties ###

| Attribute        | Type    | Description                                                                                                                                                                                                            |
|------------------|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`             | integer | Item ID. <i class="label label-info">read-only</i>                                                                                                                                                                     |
| `name`           | string  | Product name.                                                                                                                                                                                                          |
| `product_id`     | integer | Product ID.                                                                                                                                                                                                            |
| `variation_id`   | integer | Variation ID, if applicable.                                                                                                                                                                                           |
| `quantity`       | integer | Quantity ordered.                                                                                                                                                                                                      |
| `tax_class`      | string  | Slug of the tax class of product.                                                                                                                                                                                      |
| `subtotal`       | string  | Line subtotal (before discounts).                                                                                                                                                                                      |
| `subtotal_tax`   | string  | Line subtotal tax (before discounts). <i class="label label-info">read-only</i>                                                                                                                                        |
| `total`          | string  | Line total (after discounts).                                                                                                                                                                                          |
| `total_tax`      | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                                                                                                            |
| `taxes`          | array   | Line taxes. See [Inventory Log - Taxes properties](#inventory-log-taxes-properties) <i class="label label-info">read-only</i>                                                                                          |
| `meta_data`      | array   | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties)                                                                                                                             |
| `sku`            | string  | Product SKU. <i class="label label-info">read-only</i>                                                                                                                                                                 |
| `price`          | string  | Product price. <i class="label label-info">read-only</i>                                                                                                                                                               |
| `mi_inventories` | array   | Multi-Inventory order items.  See [Inventory Log - MI Order Items properties](#inventory-log-mi-order-items-properties-multi-inventory) <i class="label label-addon">Multi-Inventory</i>                               |
| `bom_items`      | array   | BOM order items.  See [Inventory Log - BOM Order Items properties](#inventory-log-bom-order-items-properties-product-levels) <i class="label label-info">read-only</i> <i class="label label-addon">Product Levels</i> |

### Inventory Log - Tax lines properties ###

| Attribute            | Type    | Description                                                                                |
|----------------------|---------|--------------------------------------------------------------------------------------------|
| `id`                 | integer | Item ID. <i class="label label-info">read-only</i>                                         |
| `rate_code`          | string  | Tax rate code. <i class="label label-info">read-only</i>                                   |
| `rate_id`            | string  | Tax rate ID. <i class="label label-info">read-only</i>                                     |
| `label`              | string  | Tax rate label. <i class="label label-info">read-only</i>                                  |
| `compound`           | boolean | Show if is a compound tax rate. <i class="label label-info">read-only</i>                  |
| `tax_total`          | string  | Tax total (not including shipping taxes). <i class="label label-info">read-only</i>        |
| `shipping_tax_total` | string  | Shipping tax total. <i class="label label-info">read-only</i>                              |
| `meta_data`          | array   | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties) |

### Inventory Log - Shipping lines properties ###

| Attribute      | Type    | Description                                                                                                                   |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------|
| `id`           | integer | Item ID. <i class="label label-info">read-only</i>                                                                            |
| `method_title` | string  | Shipping method name.                                                                                                         |
| `method_id`    | string  | Shipping method ID.                                                                                                           |
| `total`        | string  | Line total (after discounts).                                                                                                 |
| `total_tax`    | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                   |
| `taxes`        | array   | Line taxes. See [Inventory Log - Taxes properties](#inventory-log-taxes-properties) <i class="label label-info">read-only</i> |
| `meta_data`    | array   | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties)                                    |

### Inventory Log - Fee lines properties ###

| Attribute    | Type    | Description                                                                                                                   |
|--------------|---------|-------------------------------------------------------------------------------------------------------------------------------|
| `id`         | integer | Item ID. <i class="label label-info">read-only</i>                                                                            |
| `name`       | string  | Fee name.                                                                                                                     |
| `tax_class`  | string  | Tax class of fee.                                                                                                             |
| `tax_status` | string  | Tax status of fee. Options: `taxable` and `none`.                                                                             |
| `total`      | string  | Line total (after discounts).                                                                                                 |
| `total_tax`  | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                   |
| `taxes`      | array   | Line taxes. See [Inventory Log - Taxes properties](#inventory-log-taxes-properties) <i class="label label-info">read-only</i> |
| `meta_data`  | array   | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties)                                    |

### Inventory Log - Taxes properties ###

| Attribute            | Type    | Description                                                                                |
|----------------------|---------|--------------------------------------------------------------------------------------------|
| `id`                 | integer | Item ID. <i class="label label-info">read-only</i>                                         |
| `rate_code`          | string  | Tax rate code. <i class="label label-info">read-only</i>                                   |
| `rate_id`            | string  | Tax rate ID. <i class="label label-info">read-only</i>                                     |
| `label`              | string  | Tax rate label. <i class="label label-info">read-only</i>                                  |
| `compound`           | boolean | Show if is a compound tax rate. <i class="label label-info">read-only</i>                  |
| `tax_total`          | string  | Tax total (not including shipping taxes). <i class="label label-info">read-only</i>        |
| `shipping_tax_total` | string  | Shipping tax total. <i class="label label-info">read-only</i>                              |
| `meta_data`          | array   | Meta data. See [Inventory Log - Meta data properties](#inventory-log-meta-data-properties) |

### Inventory Log - MI Order Items properties <i class="label label-addon">Multi-Inventory</i> ###

| Attribute       | Type    | Description                                                                                                                |
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------|
| `id`            | integer | The order item inventory ID.                                                                                               |
| `delete`        | boolean | Set to true to delete the order item inventory with the specified inventory ID. <i class="label label-info">write-only</i> |
| `order_item_id` | integer | The order item ID linked to this order item inventory.                                                                     |
| `inventory_id`  | integer | The inventory ID linked to the order item.                                                                                 |
| `product_id`    | integer | The product ID from where the inventory comes.                                                                             |
| `qty`           | number  | The quantity of the specified inventory that is used on the order item.                                                    |
| `order_type`    | integer | The type of order (WC Order = `1`, Purchase Order = `2`, Inventory Log = `3`).                                             |
| `subtotal`      | number  | Order item inventory's subtotal.                                                                                           |
| `total`         | number  | Order item inventory's total.                                                                                              |
| `refund_qty`    | number  | Order item inventory's refund quantity.                                                                                    |
| `refund_total`  | number  | Order item inventory's refund total.  

### Inventory Log - BOM Order Items properties <i class="label label-addon">Product Levels</i> ###

| Attribute  | Type    | Description                                                                                                  |
|------------|---------|--------------------------------------------------------------------------------------------------------------|
| `id`       | integer | The BOM order item ID. <i class="label label-info">read-only</i>                                             |
| `bom_id`   | integer | The BOM product ID associated to the BOM order item.  <i class="label label-info">read-only</i>              |
| `bom_type` | string  | The BOM product type. Options: `product_part` and `raw_material`.  <i class="label label-info">read-only</i> |                                                                         |
| `qty`      | number  | The quantity of the specified BOM that is used on the order item.  <i class="label label-info">read-only</i> |                                                                                      |

## Create an inventory log ##

This API helps you to create a new inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/inventory-logs \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "type": "reserved-stock",
  "reservation_date": "2019-11-11T11:26:41",
  "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  "status": "atum_pending",
  "line_items": [
    {
      "product_id": 93,
      "quantity": 2,
      "mi_inventories": [
        {
          "inventory_id": 152,
          "qty": 1
        },
        {
          "inventory_id": 126,
          "qty": 1
        }
      ]
    },
    {
      "product_id": 22,
      "variation_id": 23,
      "quantity": 1,
      "mi_inventories": [
        {
          "inventory_id": 112,
          "qty": 1
        }        
      ]
    }
  ],
  "shipping_lines": [
    {
      "method_id": "flat_rate",
      "method_title": "Flat Rate",
      "total": "10"
    }
  ]
}'
```

```javascript
const data = {
   type: "reserved-stock",
   reservation_date: "2019-11-11T11:26:41",
   description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
   status: "atum_pending",
   line_items: [
     {
       product_id: 93,
       quantity: 2,
       mi_inventories: [
         {
          inventory_id: 152,
          qty: 1
         },
         {
          inventory_id: 126,
          qty: 1
         }
       ]
     },
     {
       product_id: 22,
       variation_id: 23,
       quantity: 1,
       mi_inventories: [
         {
           inventory_id: 112,
           qty: 1
         }        
       ]
     }
   ],
   shipping_lines: [
     {
       method_id: "flat_rate",
       method_title: "Flat Rate",
       total: "10"
     }
   ]
};

WooCommerce.post("atum/inventory-logs", data)
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
  'type' => 'reserved-stock',
  'reservation_date' => '2019-11-11T11:26:41',
  'description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.',
  'status' => 'atum_pending',
  'line_items' => [
    [
      'product_id' => 93,
      'quantity' => 2,
      'mi_inventories' => [
        [
          'inventory_id' => 152,
          'qty' => 1
        ],
        [
          'inventory_id' => 126,
          'qty' => 1
        ]
      ]
    ],
    [
      'product_id' => 22,
      'variation_id' => 23,
      'quantity' => 1,
      'mi_inventories' => [
        [
          'inventory_id' => 112,
          'qty' => 1
        ]        
      ]
    ]
  ],
  'shipping_lines' => [
    [
      'method_id' => 'flat_rate',
      'method_title' => 'Flat Rate',
      'total' => '10'
    ]
  ]
];

print_r($woocommerce->post('atum/inventory-logs', $data));
?>
```

```python
data = {
 "type": "reserved-stock",
 "reservation_date": "2019-11-11T11:26:41",
 "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
 "status": "atum_pending",
 "line_items": [
   {
     "product_id": 93,
     "quantity": 2,
     "mi_inventories": [
       {
          "inventory_id": 152,
          "qty": 1
       },
       {
          "inventory_id": 126,
          "qty": 1
       }
     ]
   },
   {
     "product_id": 22,
     "variation_id": 23,
     "quantity": 1,
     "mi_inventories": [
       {
         "inventory_id": 112,
         "qty": 1
       }        
     ]
   }
 ],
 "shipping_lines": [
   {
     "method_id": "flat_rate",
     "method_title": "Flat Rate",
     "total": "10"
   }
 ]
}

print(wcapi.post("atum/inventory-logs", data).json())
```

```ruby
data = {
 type: "reserved-stock",
 reservation_date: "2019-11-11T11:26:41",
 description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
 status: "atum_pending",
 line_items: [
   {
     product_id: 93,
     quantity: 2,
     mi_inventories: [
       {
          inventory_id: 152,
          qty: 1
       },
       {
          inventory_id: 126,
          qty: 1
       }
     ]
   },
   {
     product_id: 22,
     variation_id: 23,
     quantity: 1,
     mi_inventories: [
       {
         inventory_id: 112,
         qty: 1
       }        
     ]
   }
 ],
 shipping_lines: [
   {
     method_id: "flat_rate",
     method_title: "Flat Rate",
     total: "10"
   }
 ]
}

woocommerce.post("atum/inventory-logs", data).parsed_response
```

> JSON response example:

```json
{
    "id": 2144,
    "status": "atum_pending",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-11-11T11:43:49",
    "date_modified": "2019-11-11T11:43:50",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "20.00",
    "shipping_tax": "2.00",
    "cart_tax": "1.20",
    "total": "35.20",
    "total_tax": "3.20",
    "date_completed": "2019-11-11T11:43:51",
    "line_items": [
        {
            "id": 320,
            "name": "Woo Single #1",
            "product_id": 93,
            "variation_id": 0,
            "quantity": 2,
            "tax_class": "",
            "subtotal": "6.00",
            "subtotal_tax": "1.20",
            "total": "6.00",
            "total_tax": "1.20",
            "taxes": [
                {
                    "id": 1,
                    "total": "1.2",
                    "subtotal": "1.2"
                }
            ],
            "meta_data": [],
            "sku": "Back Orders",
            "price": 3,
            "mi_inventories": [
                {
                    "id": 192,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 193,
                    "inventory_id": 126,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 194,
                    "inventory_id": 112,
                    "qty": 1,
                    "subtotal": 0,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                }
            ],
            "bom_items": []
        },
        {
            "id": 321,
            "name": "Ship Your Idea 2 - Black",
            "product_id": 22,
            "variation_id": 23,
            "quantity": 1,
            "tax_class": "",
            "subtotal": "0.00",
            "subtotal_tax": "0.00",
            "total": "0.00",
            "total_tax": "0.00",
            "taxes": [
                {
                    "id": 1,
                    "total": "0",
                    "subtotal": "0"
                }
            ],
            "meta_data": {
                "9": {
                    "id": "2750",
                    "key": "pa_color",
                    "value": "black"
                }
            },
            "sku": "",
            "price": 0,
            "mi_inventories": [],
            "bom_items": []
        }
    ],
    "tax_lines": [
        {
            "id": 323,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "1.20",
            "shipping_tax_total": "2.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [
        {
            "id": 322,
            "method_title": "Flat Rate",
            "method_id": "flat_rate",
            "total": "10.00",
            "total_tax": "2.00",
            "taxes": [
                {
                    "id": 1,
                    "total": "2",
                    "subtotal": ""
                }
            ],
            "meta_data": []
        }
    ],
    "fee_lines": [],
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "type": "reserved-stock",
    "order": false,
    "reservation_date": "2019-11-11T11:26:41",
    "date_created_gmt": "2019-11-11T10:43:49",
    "date_modified_gmt": "2019-11-11T11:43:50",
    "date_completed_gmt": "2019-11-11T10:43:51",
    "reservation_date_gmt": "2019-11-11T10:26:41",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/2144"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
            }
        ]
    }
}
```

## Retrieve an inventory log ##

This API lets you retrieve and view a specific inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inventory-logs/727 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inventory-logs/713")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inventory-logs/713')); ?>
```

```python
print(wcapi.get("atum/inventory-logs/713").json())
```

```ruby
woocommerce.get("atum/inventory-logs/713").parsed_response
```

> JSON response example:

```json
{
    "id": 713,
    "status": "atum_pending",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-04-09T10:53:00",
    "date_modified": "2019-11-11T11:26:27",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "0.00",
    "shipping_tax": "0.00",
    "cart_tax": "0.00",
    "total": "25.32",
    "total_tax": "0.00",
    "date_completed": "2019-11-11T12:01:13",
    "line_items": [
        {
            "id": 262,
            "name": "ABC 123 XPTO",
            "product_id": 507,
            "variation_id": 0,
            "quantity": 2,
            "tax_class": "",
            "subtotal": "25.32",
            "subtotal_tax": "0.00",
            "total": "25.32",
            "total_tax": "0.00",
            "taxes": [],
            "meta_data": [],
            "sku": "",
            "price": 12.66,
            "mi_inventories": [
                {
                    "id": 187,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 20,
                    "total": 20,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 188,
                    "inventory_id": 55,
                    "qty": 1,
                    "subtotal": 5.32,
                    "total": 5.32,
                    "refund_qty": 0,
                    "refund_total": 0
                }
            ],
            "bom_items": []
        }
    ],
    "tax_lines": [],
    "shipping_lines": [],
    "fee_lines": [],
    "description": "The description",
    "type": "reserved-stock",
    "order": false,
    "reservation_date": "2019-11-11T12:01:14",
    "date_created_gmt": "2019-04-09T10:53:00",
    "date_modified_gmt": "2019-11-11T11:26:27",
    "date_completed_gmt": "2019-11-11T11:01:13",
    "reservation_date_gmt": "2019-11-11T11:01:14",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                       |
|-----------|--------|---------------------------------------------------|
| `dp`      | string | Number of decimal points to use in each resource. |

## List all inventory logs ##

This API helps you to view all the inventory logs.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/inventory-logs \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/inventory-logs")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/inventory-logs')); ?>
```

```python
print(wcapi.get("atum/inventory-logs").json())
```

```ruby
woocommerce.get("atum/inventory-logs").parsed_response
```

> JSON response example:

```json
[   
    {
        "id": 713,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2019-04-09T10:53:00",
        "date_modified": "2019-11-11T11:26:27",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "0.00",
        "total": "25.32",
        "total_tax": "0.00",
        "date_completed": "2019-11-11T12:15:14",
        "line_items": [
            {
                "id": 262,
                "name": "ABC 123 XPTO",
                "product_id": 507,
                "variation_id": 0,
                "quantity": 2,
                "tax_class": "",
                "subtotal": "25.32",
                "subtotal_tax": "0.00",
                "total": "25.32",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": [],
                "sku": "",
                "price": 12.66,
                "mi_inventories": [
                    {
                        "id": 187,
                        "inventory_id": 152,
                        "qty": 1,
                        "subtotal": 20,
                        "total": 20,
                        "refund_qty": 0,
                        "refund_total": 0
                    },
                    {
                        "id": 188,
                        "inventory_id": 55,
                        "qty": 1,
                        "subtotal": 5.32,
                        "total": 5.32,
                        "refund_qty": 0,
                        "refund_total": 0
                    }
                ],
                "bom_items": []
            }
        ],
        "tax_lines": [],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "The description",
        "type": "reserved-stock",
        "order": false,
        "reservation_date": "2019-11-11T12:15:14",
        "date_created_gmt": "2019-04-09T10:53:00",
        "date_modified_gmt": "2019-11-11T11:26:27",
        "date_completed_gmt": "2019-11-11T11:15:14",
        "reservation_date_gmt": "2019-11-11T11:15:14",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                }
            ]
        }
    },    
    {
        "id": 493,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2018-03-06T08:03:00",
        "date_modified": "2019-09-17T11:42:36",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "4.20",
        "total": "25.20",
        "total_tax": "4.20",
        "date_completed": "2019-11-11T12:15:14",
        "line_items": [
            {
                "id": 220,
                "name": "Ship Your Idea 2 - Green",
                "product_id": 22,
                "variation_id": 24,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "20.00",
                "subtotal_tax": "4.00",
                "total": "20.00",
                "total_tax": "4.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "4",
                        "subtotal": "4"
                    }
                ],
                "meta_data": {
                    "9": {
                        "id": "1727",
                        "key": "pa_color",
                        "value": "green"
                    },
                    "11": {
                        "id": "1873",
                        "key": "_order_id",
                        "value": "490"
                    }
                },
                "sku": "",
                "price": 20,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 237,
                "name": "ABC 123 XPTO",
                "product_id": 507,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "1.00",
                "subtotal_tax": "0.20",
                "total": "1.00",
                "total_tax": "0.20",
                "taxes": [
                    {
                        "id": 1,
                        "total": "0.2",
                        "subtotal": "0.2"
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 1,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 248,
                "name": "Woo Ninja",
                "product_id": 47,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "35.00",
                "subtotal_tax": "0.00",
                "total": "35.00",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": [],
                "sku": "",
                "price": 35,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 249,
                "name": "Woo Logo",
                "product_id": 79,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "15.00",
                "subtotal_tax": "0.00",
                "total": "15.00",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": [],
                "sku": "",
                "price": 15,
                "mi_inventories": [],
                "bom_items": []
            }
        ],
        "tax_lines": [
            {
                "id": 221,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "4.20",
                "shipping_tax_total": "0.00",
                "meta_data": []
            }
        ],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "",
        "type": "other",
        "order": {},
        "custom_name": "Destroyed",
        "date_created_gmt": "2018-03-06T08:03:00",
        "date_modified_gmt": "2019-09-17T11:42:36",
        "date_completed_gmt": "2019-11-11T11:15:14",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/493"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                }
            ]
        }
    },
    {
        "id": 492,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2018-03-05T09:55:00",
        "date_modified": "2019-04-26T13:43:31",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "4.60",
        "total": "39.60",
        "total_tax": "4.60",
        "date_completed": "2019-11-11T12:15:14",
        "line_items": [
            {
                "id": 219,
                "name": "Ship Your Idea 2 - Green",
                "product_id": 22,
                "variation_id": 24,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "20.00",
                "subtotal_tax": "4.00",
                "total": "20.00",
                "total_tax": "4.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "4",
                        "subtotal": "4"
                    }
                ],
                "meta_data": {
                    "9": {
                        "id": "1716",
                        "key": "pa_color",
                        "value": "green"
                    },
                    "10": {
                        "id": "2188",
                        "key": "_order_id",
                        "value": "490"
                    }
                },
                "sku": "",
                "price": 20,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 238,
                "name": "ABC 123 XPTO",
                "product_id": 507,
                "variation_id": 0,
                "quantity": 3,
                "tax_class": "",
                "subtotal": "3.00",
                "subtotal_tax": "0.60",
                "total": "3.00",
                "total_tax": "0.60",
                "taxes": [
                    {
                        "id": 1,
                        "total": "0.6",
                        "subtotal": "0.6"
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 1,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 272,
                "name": "Happy Ninja",
                "product_id": 37,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "12.00",
                "subtotal_tax": "0.00",
                "total": "12.00",
                "total_tax": "0.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "",
                        "subtotal": ""
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 12,
                "mi_inventories": [
                    {
                        "id": 131,
                        "inventory_id": 11,
                        "qty": 1,
                        "subtotal": 12,
                        "total": 12,
                        "refund_qty": 0,
                        "refund_total": 0
                    }
                ],
                "bom_items": []
            }
        ],
        "tax_lines": [
            {
                "id": 217,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "4.60",
                "shipping_tax_total": "0.00",
                "meta_data": []
            }
        ],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "",
        "type": "lost-in-post",
        "order": false,
        "shipping_company": "",
        "date_created_gmt": "2018-03-05T09:55:00",
        "date_modified_gmt": "2019-04-26T13:43:31",
        "date_completed_gmt": "2019-11-11T11:15:14",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/492"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                }
            ]
        }
    },       
    {
        "id": 317,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2017-07-06T16:29:00",
        "date_modified": "2019-04-26T11:23:03",
        "discount_total": "-15.00",
        "discount_tax": "0.00",
        "shipping_total": "2.00",
        "shipping_tax": "0.40",
        "cart_tax": "7.00",
        "total": "71.40",
        "total_tax": "7.40",
        "date_completed": "2019-11-11T12:15:15",
        "line_items": [
            {
                "id": 87,
                "name": "Woo Ninja",
                "product_id": 47,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "35.00",
                "subtotal_tax": "7.00",
                "total": "35.00",
                "total_tax": "7.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "7",
                        "subtotal": "7"
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 35,
                "mi_inventories": [
                    {
                        "id": 76,
                        "inventory_id": 82,
                        "qty": 1,
                        "subtotal": 20,
                        "total": 20,
                        "refund_qty": 0,
                        "refund_total": 0
                    }
                ],
                "bom_items": []
            },
            {
                "id": 273,
                "name": "Happy Ninja",
                "product_id": 37,
                "variation_id": 0,
                "quantity": 4,
                "tax_class": "",
                "subtotal": "27.00",
                "subtotal_tax": "0.00",
                "total": "27.00",
                "total_tax": "0.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "",
                        "subtotal": ""
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 6.75,
                "mi_inventories": [
                    {
                        "id": 132,
                        "inventory_id": 11,
                        "qty": 1,
                        "subtotal": 12,
                        "total": 12,
                        "refund_qty": 0,
                        "refund_total": 0
                    },
                    {
                        "id": 133,
                        "inventory_id": 10,
                        "qty": 1,
                        "subtotal": 5,
                        "total": 5,
                        "refund_qty": 0,
                        "refund_total": 0
                    },
                    {
                        "id": 134,
                        "inventory_id": 13,
                        "qty": 1,
                        "subtotal": 5,
                        "total": 5,
                        "refund_qty": 0,
                        "refund_total": 0
                    },
                    {
                        "id": 135,
                        "inventory_id": 12,
                        "qty": 1,
                        "subtotal": 5,
                        "total": 5,
                        "refund_qty": 0,
                        "refund_total": 0
                    }
                ],
                "bom_items": []
            }
        ],
        "tax_lines": [
            {
                "id": 89,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "7.00",
                "shipping_tax_total": "0.40",
                "meta_data": []
            }
        ],
        "shipping_lines": [
            {
                "id": 88,
                "method_title": "Shipping",
                "method_id": "flat_rate",
                "total": "2.00",
                "total_tax": "0.40",
                "taxes": [
                    {
                        "id": 1,
                        "total": "0.4",
                        "subtotal": ""
                    }
                ],
                "meta_data": []
            }
        ],
        "fee_lines": [],
        "description": "",
        "type": "warehouse-damage",
        "order": false,
        "damage_date": "2019-11-11T12:15:15",
        "date_created_gmt": "2017-07-06T16:29:00",
        "date_modified_gmt": "2019-04-26T11:23:03",
        "date_completed_gmt": "2019-11-11T11:15:15",
        "damage_date_gmt": "2019-11-11T11:15:15",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/317"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                }
            ]
        }
    },   
    {
        "id": 314,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2017-07-06T15:48:00",
        "date_modified": "2017-07-06T16:06:28",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "2.00",
        "shipping_tax": "0.40",
        "cart_tax": "7.00",
        "total": "44.40",
        "total_tax": "7.40",
        "date_completed": "2019-11-11T12:15:15",
        "line_items": [
            {
                "id": 81,
                "name": "Woo Logo",
                "product_id": 60,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "35.00",
                "subtotal_tax": "7.00",
                "total": "35.00",
                "total_tax": "7.00",
                "taxes": [
                    {
                        "id": 1,
                        "total": "7",
                        "subtotal": "7"
                    }
                ],
                "meta_data": [],
                "sku": "",
                "price": 35,
                "mi_inventories": [],
                "bom_items": []
            }
        ],
        "tax_lines": [
            {
                "id": 83,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "7.00",
                "shipping_tax_total": "0.40",
                "meta_data": []
            }
        ],
        "shipping_lines": [
            {
                "id": 82,
                "method_title": "Shipping",
                "method_id": "flat_rate",
                "total": "2.00",
                "total_tax": "0.40",
                "taxes": [
                    {
                        "id": 1,
                        "total": "0.4",
                        "subtotal": ""
                    }
                ],
                "meta_data": []
            }
        ],
        "fee_lines": [],
        "description": "",
        "type": "customer-returns",
        "order": false,
        "return_date": "2019-11-11T12:15:15",
        "date_created_gmt": "2017-07-06T15:48:00",
        "date_modified_gmt": "2017-07-06T16:06:28",
        "date_completed_gmt": "2019-11-11T11:15:15",
        "return_date_gmt": "2019-11-11T11:15:15",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/314"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter          | Type    | Description                                                                                                                                                       |
|--------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`          | string  | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                      |
| `page`             | integer | Current page of the collection. Default is `1`.                                                                                                                   |
| `per_page`         | integer | Maximum number of items to be returned in result set. Default is `10`.                                                                                            |
| `search`           | string  | Limit results to those matching a string.                                                                                                                         |
| `after`            | string  | Limit response to resources published after a given ISO8601 compliant date.                                                                                       |
| `before`           | string  | Limit response to resources published before a given ISO8601 compliant date.                                                                                      |
| `exclude`          | array   | Ensure result set excludes specific IDs.                                                                                                                          |
| `include`          | array   | Limit result set to specific ids.                                                                                                                                 |
| `offset`           | integer | Offset the result set by a specific number of items.                                                                                                              |
| `order`            | string  | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                       |
| `orderby`          | string  | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                     |
| `parent`           | array   | Limit result set to those of particular parent IDs.                                                                                                               |
| `parent_exclude`   | array   | Limit result set to all items except those of a particular parent ID.                                                                                             |
| `status`           | array   | Limit result set to inventory logs assigned a specific status. Options: `any`, `atum_pending`, `atum_completed` and `trash`. Default is `any`.                    |
| `product`          | integer | Limit result set to inventory logs assigned a specific product.                                                                                                   |
| `dp`               | integer | Number of decimal points to use in each resource. Default is `2`.                                                                                                 |
| `type`             | array   | Limit result set to inventory logs of the specified type(s). Options: `reserved-stock`, `customer-returns`, `warehouse-damage`, `lost-in-post`, `other`.          |
| `order_id`         | integer | Limit result set to inventory logs linked to the specified WC order ID.                                                                                           |
| `reservation_date` | string  | Limit result set to inventory logs with the reservation date set on a given ISO8601 compliant date. Only available for inventory logs with type `reserved-stock`. |
| `return_date`      | string  | Limit result set to inventory logs with the return date set on a given ISO8601 compliant date. Only available for inventory logs with type `customer-returns`.    |
| `damage_date`      | string  | Limit result set to inventory logs with the damage date set on a given ISO8601 compliant date. Only available for inventory logs with type `warehouse-damage`.    |
| `shipping_company` | string  | Limit result set to the inventory logs where the specified company lost the stock in post. Only available for inventory logs with type `lost-in-post`.            |
| `custom_name`      | string  | Limit result set to the inventory logs with type 'other' and the specified custom name.                                                                           |

## Update an Invetory log ##

This API lets you make changes to an inventory log.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/atum/inventory-logs/713 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
          "status": "atum_completed"
        }'
```

```javascript
const data = {
   status: "atum_completed"
 };

WooCommerce.put("atum/inventory-logs/713", data)
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
  'status' => 'atum_completed'
];

print_r($woocommerce->put('atum/inventory-logs/713', $data));
?>
```

```python
data = {
 "status": "atum_completed"
}

print(wcapi.put("atum/inventory-logs/713", data).json())
```

```ruby
data = {
 status: "atum_completed"
}

woocommerce.put("atum/inventory-logs/713", data).parsed_response
```

> JSON response example:

```json
{
    "id": 713,
    "status": "atum_completed",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-04-09T10:53:00",
    "date_modified": "2019-11-11T12:41:09",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "0.00",
    "shipping_tax": "0.00",
    "cart_tax": "0.00",
    "total": "25.32",
    "total_tax": "0.00",
    "date_completed": "2019-11-11T12:41:09",
    "line_items": [
        {
            "id": 262,
            "name": "ABC 123 XPTO",
            "product_id": 507,
            "variation_id": 0,
            "quantity": 2,
            "tax_class": "",
            "subtotal": "25.32",
            "subtotal_tax": "0.00",
            "total": "25.32",
            "total_tax": "0.00",
            "taxes": [],
            "meta_data": [],
            "sku": "",
            "price": 12.66,
            "mi_inventories": [
                {
                    "id": 187,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 20,
                    "total": 20,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 188,
                    "inventory_id": 55,
                    "qty": 1,
                    "subtotal": 5.32,
                    "total": 5.32,
                    "refund_qty": 0,
                    "refund_total": 0
                }
            ],
            "bom_items": []
        }
    ],
    "tax_lines": [],
    "shipping_lines": [],
    "fee_lines": [],
    "description": "The description",
    "type": "",
    "order": false,
    "date_created_gmt": "2019-04-09T10:53:00",
    "date_modified_gmt": "2019-11-11T12:41:09",
    "date_completed_gmt": "2019-11-11T11:41:09",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/713"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
            }
        ]
    }
}
```

## Delete an inventory log ##

This API helps you delete an inventory log.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/atum/inventory-logs/2144?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("atum/inventory-logs/2144", {
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
<?php print_r($woocommerce->delete('atum/inventory-logs/2144', ['force' => true])); ?>
```

```python
print(wcapi.delete("atum/inventory-logs/2144", params={"force": True}).json())
```

```ruby
woocommerce.delete("atum/inventory-logs/2144", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 2144,
    "status": "atum_pending",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-11-11T11:43:49",
    "date_modified": "2019-11-11T11:43:50",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "20.00",
    "shipping_tax": "2.00",
    "cart_tax": "1.20",
    "total": "35.20",
    "total_tax": "3.20",
    "date_completed": "2019-11-11T12:45:13",
    "line_items": [
        {
            "id": 320,
            "name": "Woo Single #1",
            "product_id": 93,
            "variation_id": 0,
            "quantity": 2,
            "tax_class": "",
            "subtotal": "6.00",
            "subtotal_tax": "1.20",
            "total": "6.00",
            "total_tax": "1.20",
            "taxes": [
                {
                    "id": 1,
                    "total": "1.2",
                    "subtotal": "1.2"
                }
            ],
            "meta_data": [],
            "sku": "Back Orders",
            "price": 3,
            "mi_inventories": [
                {
                    "id": 192,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 193,
                    "inventory_id": 126,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 194,
                    "inventory_id": 112,
                    "qty": 1,
                    "subtotal": 0,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                }
            ],
            "bom_items": []
        },
        {
            "id": 321,
            "name": "Ship Your Idea 2 - Black",
            "product_id": 22,
            "variation_id": 23,
            "quantity": 1,
            "tax_class": "",
            "subtotal": "0.00",
            "subtotal_tax": "0.00",
            "total": "0.00",
            "total_tax": "0.00",
            "taxes": [
                {
                    "id": 1,
                    "total": "0",
                    "subtotal": "0"
                }
            ],
            "meta_data": {
                "9": {
                    "id": "2750",
                    "key": "pa_color",
                    "value": "black"
                }
            },
            "sku": "",
            "price": 0,
            "mi_inventories": [],
            "bom_items": []
        }
    ],
    "tax_lines": [
        {
            "id": 323,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "1.20",
            "shipping_tax_total": "2.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [
        {
            "id": 322,
            "method_title": "Flat Rate",
            "method_id": "flat_rate",
            "total": "10.00",
            "total_tax": "2.00",
            "taxes": [
                {
                    "id": 1,
                    "total": "2",
                    "subtotal": ""
                }
            ],
            "meta_data": []
        }
    ],
    "fee_lines": [],
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "type": "reserved-stock",
    "order": false,
    "reservation_date": "2019-11-11T11:26:41",
    "date_created_gmt": "2019-11-11T10:43:49",
    "date_modified_gmt": "2019-11-11T11:43:50",
    "date_completed_gmt": "2019-11-11T11:45:13",
    "reservation_date_gmt": "2019-11-11T10:26:41",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/2144"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                                     |
|-----------|--------|---------------------------------------------------------------------------------|
| `force`   | string | Use `true` whether to permanently delete the inventory log, Default is `false`. |

## Batch update inventory logs ##

This API helps you to batch create, update and delete multiple inventory logs.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/inventory-logs/batch</h6>
	</div>
</div>

> Example of Create, Update and Delete items in bulk:

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/inventory-logs/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "create": [
        {
          "type": "lost-in-post",
          "shipping_company": "UPS",
          "line_items": [
            {
              "product_id": 79,
              "quantity": 1,
              "mi_inventories": [
                {
                  "inventory_id": 13,
                  "qty": 1
                }
              ] 
            },
            {
              "product_id": 93,
              "quantity": 1,
              "mi_inventories": [
                {
                  "inventory_id": 14,
                  "qty": 1
                }
              ] 
            },
            {
              "product_id": 22,
              "variation_id": 23,
              "quantity": 1,
              "mi_inventories": [
                {
                  "inventory_id": 58,
                  "qty": 1
                }
              ] 
            }
          ],
          "shipping_lines": [
            {
              "method_id": "flat_rate",
              "method_title": "Flat Rate",
              "total": 30
            }
          ]
        },
        {
          "type": "other",
          "custom_name": "Storm",
          "line_items": [
            {
              "product_id": 22,
              "variation_id": 23,
              "quantity": 1,
              "mi_inventories": [
                {
                  "inventory_id": 59,
                  "qty": 1
                }
              ] 
            },
            {
              "product_id": 22,
              "variation_id": 24,
              "quantity": 1
            }
          ],
          "shipping_lines": [
            {
              "method_id": "flat_rate",
              "method_title": "Flat Rate",
              "total": 20
            }
          ]
        }
      ],
      "update": [
        {
          "id": 492,
          "type": "warehouse-damage",
          "damage_date": "2019-11-11T12:15:14"
        }
      ],
      "delete": [
        2147
      ]
    }'
```

```javascript
const data = {
   create: [
     {
       type: "lost-in-post",
       shipping_company: "UPS",
       line_items: [
         {
           product_id: 79,
           quantity: 1,
           mi_inventories: [
             {
               inventory_id: 13,
               qty: 1
             }
           ] 
         },
         {
           product_id: 93,
           quantity: 1,
           mi_inventories: [
             {
               inventory_id: 14,
               qty: 1
             }
           ] 
         },
         {
           product_id: 22,
           variation_id: 23,
           quantity: 1,
           mi_inventories: [
             {
               inventory_id: 58,
               qty: 1
             }
           ] 
         }
       ],
       shipping_lines: [
         {
           method_id: "flat_rate",
           method_title: "Flat Rate",
           total: 30
         }
       ]
     },
     {
       type: "other",
       custom_name: "Storm",
       line_items: [
         {
           product_id: 22,
           variation_id: 23,
           quantity: 1,
           mi_inventories: [
             {
               inventory_id: 59,
               qty: 1
             }
           ] 
         },
         {
           product_id: 22,
           variation_id: 24,
           quantity: 1
         }
       ],
       shipping_lines: [
         {
           method_id: "flat_rate",
           method_title: "Flat Rate",
           total: 20
         }
       ]
     }
   ],
   update: [
     {
       id: 492,
       type: "warehouse-damage",
       damage_date: "2019-11-11T12:15:14"
     }
   ],
   delete: [
     2147
   ]
};

WooCommerce.post("atum/inventory-logs/batch", data)
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
      'type' => 'lost-in-post',
      'shipping_company' => 'UPS',
      'line_items' => [
        [
          'product_id' => 79,
          'quantity' => 1,
          'mi_inventories' => [
            [
              'inventory_id' => 13,
              'qty' => 1
            ]
          ] 
        ],
        [
          'product_id' => 93,
          'quantity' => 1,
          'mi_inventories' => [
            [
              'inventory_id' => 14,
              'qty' => 1
            ]
          ] 
        ],
        [
          'product_id' => 22,
          'variation_id' => 23,
          'quantity' => 1,
          'mi_inventories' => [
            [
              'inventory_id' => 58,
              'qty' => 1
            ]
          ] 
        ]
      ],
      'shipping_lines' => [
        [
          'method_id' => 'flat_rate',
          'method_title' => 'Flat Rate',
          'total' => 30
        ]
      ]
    ],
    [
      'type' => 'other',
      'custom_name' => 'Storm',
      'line_items' => [
        [
          'product_id' => 22,
          'variation_id' => 23,
          'quantity' => 1,
          'mi_inventories' => [
            [
              'inventory_id' => 59,
              'qty' => 1
            ]
          ] 
        ],
        [
          'product_id' => 22,
          'variation_id' => 24,
          'quantity' => 1
        ]
      ],
      'shipping_lines' => [
        [
          'method_id' => 'flat_rate',
          'method_title' => 'Flat Rate',
          'total' => 20
        ]
      ]
    ]
  ],
  'update' => [
    [
      'id' => 492,
      'type' => 'warehouse-damage',
      'damage_date' => '2019-11-11T12:15:14'
    ]
  ],
  'delete' => [
    2147
  ]
];

print_r($woocommerce->post('atum/inventory-logs/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "type": "lost-in-post",
     "shipping_company": "UPS",
     "line_items": [
       {
         "product_id": 79,
         "quantity": 1,
         "mi_inventories": [
           {
             "inventory_id": 13,
             "qty": 1
           }
         ] 
       },
       {
         "product_id": 93,
         "quantity": 1,
         "mi_inventories": [
           {
             "inventory_id": 14,
             "qty": 1
           }
         ] 
       },
       {
         "product_id": 22,
         "variation_id": 23,
         "quantity": 1,
         "mi_inventories": [
           {
             "inventory_id": 58,
             "qty": 1
           }
         ] 
       }
     ],
     "shipping_lines": [
       {
         "method_id": "flat_rate",
         "method_title": "Flat Rate",
         "total": 30
       }
     ]
   },
   {
     "type": "other",
     "custom_name": "Storm",
     "line_items": [
       {
         "product_id": 22,
         "variation_id": 23,
         "quantity": 1,
         "mi_inventories": [
           {
             "inventory_id": 59,
             "qty": 1
           }
         ] 
       },
       {
         "product_id": 22,
         "variation_id": 24,
         "quantity": 1
       }
     ],
     "shipping_lines": [
       {
         "method_id": "flat_rate",
         "method_title": "Flat Rate",
         "total": 20
       }
     ]
   }
 ],
 "update": [
   {
     "id": 492,
     "type": "warehouse-damage",
     "damage_date": "2019-11-11T12:15:14"
   }
 ],
 "delete": [
   2147
 ]
}

print(wcapi.post("atum/inventory-logs/batch", data).json())
```

```ruby
data = {
 create: [
   {
     type: "lost-in-post",
     shipping_company: "UPS",
     line_items: [
       {
         product_id: 79,
         quantity: 1,
         mi_inventories: [
           {
             inventory_id: 13,
             qty: 1
           }
         ] 
       },
       {
         product_id: 93,
         quantity: 1,
         mi_inventories: [
           {
             inventory_id: 14,
             qty: 1
           }
         ] 
       },
       {
         product_id: 22,
         variation_id: 23,
         quantity: 1,
         mi_inventories: [
           {
             inventory_id: 58,
             qty: 1
           }
         ] 
       }
     ],
     shipping_lines: [
       {
         method_id: "flat_rate",
         method_title: "Flat Rate",
         total: 30
       }
     ]
   },
   {
     type: "other",
     custom_name: "Storm",
     line_items: [
       {
         product_id: 22,
         variation_id: 23,
         quantity: 1,
         mi_inventories: [
           {
             inventory_id: 59,
             qty: 1
           }
         ] 
       },
       {
         product_id: 22,
         variation_id: 24,
         quantity: 1
       }
     ],
     shipping_lines: [
       {
         method_id: "flat_rate",
         method_title: "Flat Rate",
         total: 20
       }
     ]
   }
 ],
 update: [
   {
     id: 492,
     type: "warehouse-damage",
     damage_date: "2019-11-11T12:15:14"
   }
 ],
 delete: [
   2147
 ]
}

woocommerce.post("atum/inventory-logs/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2149,
            "status": "atum_pending",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-11-11T12:54:23",
            "date_modified": "2019-11-11T12:54:25",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "60.00",
            "shipping_tax": "6.00",
            "cart_tax": "3.60",
            "total": "105.60",
            "total_tax": "9.60",
            "date_completed": "2019-11-11T12:54:25",
            "line_items": [
                {
                    "id": 328,
                    "name": "Woo Logo",
                    "product_id": 79,
                    "variation_id": 0,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "15.00",
                    "subtotal_tax": "3.00",
                    "total": "15.00",
                    "total_tax": "3.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "3",
                            "subtotal": "3"
                        }
                    ],
                    "meta_data": [],
                    "sku": "",
                    "price": 15,
                    "mi_inventories": [
                        {
                            "id": 198,
                            "inventory_id": 13,
                            "qty": 1,
                            "subtotal": 15,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        }
                    ],
                    "bom_items": []
                },
                {
                    "id": 329,
                    "name": "Woo Single #1",
                    "product_id": 93,
                    "variation_id": 0,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "3.00",
                    "subtotal_tax": "0.60",
                    "total": "3.00",
                    "total_tax": "0.60",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "0.6",
                            "subtotal": "0.6"
                        }
                    ],
                    "meta_data": [],
                    "sku": "Back Orders",
                    "price": 3,
                    "mi_inventories": [
                        {
                            "id": 199,
                            "inventory_id": 14,
                            "qty": 1,
                            "subtotal": 3,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        },
                        {
                            "id": 200,
                            "inventory_id": 58,
                            "qty": 1,
                            "subtotal": 9,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        }
                    ],
                    "bom_items": []
                },
                {
                    "id": 330,
                    "name": "Ship Your Idea 2 - Black",
                    "product_id": 22,
                    "variation_id": 23,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "0.00",
                    "subtotal_tax": "0.00",
                    "total": "0.00",
                    "total_tax": "0.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "0",
                            "subtotal": "0"
                        }
                    ],
                    "meta_data": {
                        "9": {
                            "id": "2815",
                            "key": "pa_color",
                            "value": "black"
                        }
                    },
                    "sku": "",
                    "price": 0,
                    "mi_inventories": [],
                    "bom_items": []
                }
            ],
            "tax_lines": [
                {
                    "id": 332,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "3.60",
                    "shipping_tax_total": "6.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [
                {
                    "id": 331,
                    "method_title": "Flat Rate",
                    "method_id": "flat_rate",
                    "total": "30.00",
                    "total_tax": "6.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "6",
                            "subtotal": ""
                        }
                    ],
                    "meta_data": []
                }
            ],
            "fee_lines": [],
            "description": "",
            "type": "lost-in-post",
            "order": false,
            "shipping_company": "UPS",
            "date_created_gmt": "2019-11-11T11:54:23",
            "date_modified_gmt": "2019-11-11T12:54:25",
            "date_completed_gmt": "2019-11-11T11:54:25",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/2149"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                    }
                ]
            }
        },
        {
            "id": 2150,
            "status": "atum_pending",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-11-11T12:54:26",
            "date_modified": "2019-11-11T12:54:27",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "40.00",
            "shipping_tax": "4.00",
            "cart_tax": "4.00",
            "total": "88.00",
            "total_tax": "8.00",
            "date_completed": "2019-11-11T12:54:28",
            "line_items": [
                {
                    "id": 333,
                    "name": "Ship Your Idea 2 - Black",
                    "product_id": 22,
                    "variation_id": 23,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "0.00",
                    "subtotal_tax": "0.00",
                    "total": "0.00",
                    "total_tax": "0.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "0",
                            "subtotal": "0"
                        }
                    ],
                    "meta_data": {
                        "9": {
                            "id": "2834",
                            "key": "pa_color",
                            "value": "black"
                        }
                    },
                    "sku": "",
                    "price": 0,
                    "mi_inventories": [],
                    "bom_items": []
                },
                {
                    "id": 334,
                    "name": "Ship Your Idea 2 - Green",
                    "product_id": 22,
                    "variation_id": 24,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "20.00",
                    "subtotal_tax": "4.00",
                    "total": "20.00",
                    "total_tax": "4.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "4",
                            "subtotal": "4"
                        }
                    ],
                    "meta_data": {
                        "9": {
                            "id": "2844",
                            "key": "pa_color",
                            "value": "green"
                        }
                    },
                    "sku": "",
                    "price": 20,
                    "mi_inventories": [],
                    "bom_items": []
                }
            ],
            "tax_lines": [
                {
                    "id": 336,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "4.00",
                    "shipping_tax_total": "4.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [
                {
                    "id": 335,
                    "method_title": "Flat Rate",
                    "method_id": "flat_rate",
                    "total": "20.00",
                    "total_tax": "4.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "4",
                            "subtotal": ""
                        }
                    ],
                    "meta_data": []
                }
            ],
            "fee_lines": [],
            "description": "",
            "type": "other",
            "order": false,
            "custom_name": "Storm",
            "date_created_gmt": "2019-11-11T11:54:26",
            "date_modified_gmt": "2019-11-11T12:54:27",
            "date_completed_gmt": "2019-11-11T11:54:28",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/2150"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 492,
            "status": "atum_pending",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2018-03-05T09:55:00",
            "date_modified": "2019-11-11T12:54:28",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "0.00",
            "shipping_tax": "0.00",
            "cart_tax": "4.60",
            "total": "39.60",
            "total_tax": "4.60",
            "date_completed": "2019-11-11T12:54:29",
            "line_items": [
                {
                    "id": 219,
                    "name": "Ship Your Idea 2 - Green",
                    "product_id": 22,
                    "variation_id": 24,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "20.00",
                    "subtotal_tax": "4.00",
                    "total": "20.00",
                    "total_tax": "4.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "4",
                            "subtotal": "4"
                        }
                    ],
                    "meta_data": {
                        "9": {
                            "id": "1716",
                            "key": "pa_color",
                            "value": "green"
                        },
                        "10": {
                            "id": "2188",
                            "key": "_order_id",
                            "value": "490"
                        }
                    },
                    "sku": "",
                    "price": 20,
                    "mi_inventories": [],
                    "bom_items": []
                },
                {
                    "id": 238,
                    "name": "ABC 123 XPTO",
                    "product_id": 507,
                    "variation_id": 0,
                    "quantity": 3,
                    "tax_class": "",
                    "subtotal": "3.00",
                    "subtotal_tax": "0.60",
                    "total": "3.00",
                    "total_tax": "0.60",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "0.6",
                            "subtotal": "0.6"
                        }
                    ],
                    "meta_data": [],
                    "sku": "",
                    "price": 1,
                    "mi_inventories": [],
                    "bom_items": []
                },
                {
                    "id": 272,
                    "name": "Happy Ninja",
                    "product_id": 37,
                    "variation_id": 0,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "12.00",
                    "subtotal_tax": "0.00",
                    "total": "12.00",
                    "total_tax": "0.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "",
                            "subtotal": ""
                        }
                    ],
                    "meta_data": [],
                    "sku": "",
                    "price": 12,
                    "mi_inventories": [
                        {
                            "id": 131,
                            "inventory_id": 11,
                            "qty": 1,
                            "subtotal": 12,
                            "total": 12,
                            "refund_qty": 0,
                            "refund_total": 0
                        }
                    ],
                    "bom_items": []
                }
            ],
            "tax_lines": [
                {
                    "id": 217,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "4.60",
                    "shipping_tax_total": "0.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [],
            "fee_lines": [],
            "description": "",
            "type": "warehouse-damage",
            "order": false,
            "damage_date": "2019-11-11T12:15:14",
            "date_created_gmt": "2018-03-05T09:55:00",
            "date_modified_gmt": "2019-11-11T12:54:28",
            "date_completed_gmt": "2019-11-11T11:54:29",
            "damage_date_gmt": "2019-11-11T11:15:14",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/492"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 2147,
            "status": "atum_pending",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-11-11T12:50:49",
            "date_modified": "2019-11-11T12:50:50",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "20.00",
            "shipping_tax": "2.00",
            "cart_tax": "1.20",
            "total": "35.20",
            "total_tax": "3.20",
            "date_completed": "2019-11-11T12:54:29",
            "line_items": [
                {
                    "id": 324,
                    "name": "Woo Single #1",
                    "product_id": 93,
                    "variation_id": 0,
                    "quantity": 2,
                    "tax_class": "",
                    "subtotal": "6.00",
                    "subtotal_tax": "1.20",
                    "total": "6.00",
                    "total_tax": "1.20",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "1.2",
                            "subtotal": "1.2"
                        }
                    ],
                    "meta_data": [],
                    "sku": "Back Orders",
                    "price": 3,
                    "mi_inventories": [
                        {
                            "id": 195,
                            "inventory_id": 152,
                            "qty": 1,
                            "subtotal": 3,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        },
                        {
                            "id": 196,
                            "inventory_id": 126,
                            "qty": 1,
                            "subtotal": 3,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        },
                        {
                            "id": 197,
                            "inventory_id": 112,
                            "qty": 1,
                            "subtotal": 0,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        }
                    ],
                    "bom_items": []
                },
                {
                    "id": 325,
                    "name": "Ship Your Idea 2 - Black",
                    "product_id": 22,
                    "variation_id": 23,
                    "quantity": 1,
                    "tax_class": "",
                    "subtotal": "0.00",
                    "subtotal_tax": "0.00",
                    "total": "0.00",
                    "total_tax": "0.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "0",
                            "subtotal": "0"
                        }
                    ],
                    "meta_data": {
                        "9": {
                            "id": "2778",
                            "key": "pa_color",
                            "value": "black"
                        }
                    },
                    "sku": "",
                    "price": 0,
                    "mi_inventories": [],
                    "bom_items": []
                }
            ],
            "tax_lines": [
                {
                    "id": 327,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "1.20",
                    "shipping_tax_total": "2.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [
                {
                    "id": 326,
                    "method_title": "Flat Rate",
                    "method_id": "flat_rate",
                    "total": "10.00",
                    "total_tax": "2.00",
                    "taxes": [
                        {
                            "id": 1,
                            "total": "2",
                            "subtotal": ""
                        }
                    ],
                    "meta_data": []
                }
            ],
            "fee_lines": [],
            "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
            "type": "reserved-stock",
            "order": false,
            "reservation_date": "2019-11-11T11:26:41",
            "date_created_gmt": "2019-11-11T11:50:49",
            "date_modified_gmt": "2019-11-11T12:50:50",
            "date_completed_gmt": "2019-11-11T11:54:29",
            "reservation_date_gmt": "2019-11-11T10:26:41",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs/2147"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/inventory-logs"
                    }
                ]
            }
        }
    ]
}
```
