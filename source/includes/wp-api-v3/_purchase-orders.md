# Purchase orders #

<i class="label label-atum">ATUM</i>

The purchase orders API allows you to create, view, update, and delete individual, or a batch, of purchase orders.

## Purchase order properties ##

| Attribute            | Type      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|----------------------|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                 | integer   | Unique identifier for the resource. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `status`             | string    | Purchase order status. Options: `atum_pending`, `atum_ordered`, `atum_onthewayin`, `atum_receiving`, `atum_received` and `trash`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `currency`           | string    | Currency the purchase order was created with, in ISO format. Options: `AED`, `AFN`, `ALL`, `AMD`, `ANG`, `AOA`, `ARS`, `AUD`, `AWG`, `AZN`, `BAM`, `BBD`, `BDT`, `BGN`, `BHD`, `BIF`, `BMD`, `BND`, `BOB`, `BRL`, `BSD`, `BTC`, `BTN`, `BWP`, `BYR`, `BZD`, `CAD`, `CDF`, `CHF`, `CLP`, `CNY`, `COP`, `CRC`, `CUC`, `CUP`, `CVE`, `CZK`, `DJF`, `DKK`, `DOP`, `DZD`, `EGP`, `ERN`, `ETB`, `EUR`, `FJD`, `FKP`, `GBP`, `GEL`, `GGP`, `GHS`, `GIP`, `GMD`, `GNF`, `GTQ`, `GYD`, `HKD`, `HNL`, `HRK`, `HTG`, `HUF`, `IDR`, `ILS`, `IMP`, `INR`, `IQD`, `IRR`, `IRT`, `ISK`, `JEP`, `JMD`, `JOD`, `JPY`, `KES`, `KGS`, `KHR`, `KMF`, `KPW`, `KRW`, `KWD`, `KYD`, `KZT`, `LAK`, `LBP`, `LKR`, `LRD`, `LSL`, `LYD`, `MAD`, `MDL`, `MGA`, `MKD`, `MMK`, `MNT`, `MOP`, `MRO`, `MUR`, `MVR`, `MWK`, `MXN`, `MYR`, `MZN`, `NAD`, `NGN`, `NIO`, `NOK`, `NPR`, `NZD`, `OMR`, `PAB`, `PEN`, `PGK`, `PHP`, `PKR`, `PLN`, `PRB`, `PYG`, `QAR`, `RON`, `RSD`, `RUB`, `RWF`, `SAR`, `SBD`, `SCR`, `SDG`, `SEK`, `SGD`, `SHP`, `SLL`, `SOS`, `SRD`, `SSP`, `STD`, `SYP`, `SZL`, `THB`, `TJS`, `TMT`, `TND`, `TOP`, `TRY`, `TTD`, `TWD`, `TZS`, `UAH`, `UGX`, `USD`, `UYU`, `UZS`, `VEF`, `VND`, `VUV`, `WST`, `XAF`, `XCD`, `XOF`, `XPF`, `YER`, `ZAR` and `ZMW`. Default is `USD`. |
| `date_created`       | date-time | The date the purchase order was created, in the site's timezone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `date_created_gmt`   | date-time | The date the purchase order was created, as GMT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `date_modified`      | date-time | The date the purchase order was last modified, in the site's timezone. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `date_modified_gmt`  | date-time | The date the purchase order was last modified, as GMT. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `discount_total`     | string    | Total discount amount for the purchase order. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `discount_tax`       | string    | Total discount tax amount for the purchase order. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `shipping_total`     | string    | Total shipping amount for the purchase order. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `shipping_tax`       | string    | Total shipping tax amount for the purchase order. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `cart_tax`           | string    | Sum of line item taxes only. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `total`              | string    | Grand total. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `total_tax`          | string    | Sum of all taxes. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `prices_include_tax` | boolean   | True the prices included tax during checkout. <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `date_completed`     | date-time | The date the purchase order was completed, in the site's timezone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `date_completed_gmt` | date-time | The date the purchase order was completed, as GMT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `supplier`           | integer   | The supplier ID linked to the purchase order.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `multiple_suppliers` | boolean   | Whether the multiple_suppliers switch is enabled or not.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `date_expected`      | date-time | The date when the purchase order is expected at location, in the site's timezone.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `date_expected_gmt`  | date-time | The date when the purchase order is expected at location, as GMT.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `line_items`         | array     | Line items data. See [Purchase Order - Line items properties](#purchase-order-line-items-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `tax_lines`          | array     | Tax lines data. See [Purchase Order - Tax lines properties](#purchase-order-tax-lines-properties) <i class="label label-info">read-only</i>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `shipping_lines`     | array     | Shipping lines data. See [Purchase Order - Shipping lines properties](#purchase-order-shipping-lines-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `fee_lines`          | array     | Fee lines data. See [Purchase Order - Fee lines properties](#purchase-order-fee-lines-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `meta_data`          | array     | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `description`        | string    | The purchase order description.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Purchase Order - Meta data properties ###

| Attribute | Type    | Description                                        |
|-----------|---------|----------------------------------------------------|
| `id`      | integer | Meta ID. <i class="label label-info">read-only</i> |
| `key`     | string  | Meta key.                                          |
| `value`   | string  | Meta value.                                        |

### Purchase Order - Line items properties ###

| Attribute        | Type    | Description                                                                                                                                                                                                              |
|------------------|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`             | integer | Item ID. <i class="label label-info">read-only</i>                                                                                                                                                                       |
| `name`           | string  | Product name.                                                                                                                                                                                                            |
| `product_id`     | integer | Product ID.                                                                                                                                                                                                              |
| `variation_id`   | integer | Variation ID, if applicable.                                                                                                                                                                                             |
| `quantity`       | integer | Quantity ordered.                                                                                                                                                                                                        |
| `tax_class`      | string  | Slug of the tax class of product.                                                                                                                                                                                        |
| `subtotal`       | string  | Line subtotal (before discounts).                                                                                                                                                                                        |
| `subtotal_tax`   | string  | Line subtotal tax (before discounts). <i class="label label-info">read-only</i>                                                                                                                                          |
| `total`          | string  | Line total (after discounts).                                                                                                                                                                                            |
| `total_tax`      | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                                                                                                              |
| `taxes`          | array   | Line taxes. See [Purchase Order - Taxes properties](#purchase-order-taxes-properties) <i class="label label-info">read-only</i>                                                                                          |
| `stock_changed`  | string  | Whether the stock was already changed for this item. Options: `yes` and `no`.                                                                                                                                            |
| `meta_data`      | array   | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties)                                                                                                                             |
| `sku`            | string  | Product SKU. <i class="label label-info">read-only</i>                                                                                                                                                                   |
| `price`          | string  | Product price. <i class="label label-info">read-only</i>                                                                                                                                                                 |
| `mi_inventories` | array   | Multi-Inventory order items.  See [Purchase Order - MI Order Items properties](#purchase-order-mi-order-items-properties-multi-inventory) <i class="label label-addon">Multi-Inventory</i>                               |
| `bom_items`      | array   | BOM order items.  See [Purchase Order - BOM Order Items properties](#purchase-order-bom-order-items-properties-product-levels) <i class="label label-info">read-only</i> <i class="label label-addon">Product Levels</i> |

### Purchase Order - Tax lines properties ###

| Attribute            | Type    | Description                                                                                |
|----------------------|---------|--------------------------------------------------------------------------------------------|
| `id`                 | integer | Item ID. <i class="label label-info">read-only</i>                                         |
| `rate_code`          | string  | Tax rate code. <i class="label label-info">read-only</i>                                   |
| `rate_id`            | string  | Tax rate ID. <i class="label label-info">read-only</i>                                     |
| `label`              | string  | Tax rate label. <i class="label label-info">read-only</i>                                  |
| `compound`           | boolean | Show if is a compound tax rate. <i class="label label-info">read-only</i>                  |
| `tax_total`          | string  | Tax total (not including shipping taxes). <i class="label label-info">read-only</i>        |
| `shipping_tax_total` | string  | Shipping tax total. <i class="label label-info">read-only</i>                              |
| `meta_data`          | array   | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties) |

### Purchase Order - Shipping lines properties ###

| Attribute      | Type    | Description                                                                                                                   |
|----------------|---------|-------------------------------------------------------------------------------------------------------------------------------|
| `id`           | integer | Item ID. <i class="label label-info">read-only</i>                                                                            |
| `method_title` | string  | Shipping method name.                                                                                                         |
| `method_id`    | string  | Shipping method ID.                                                                                                           |
| `total`        | string  | Line total (after discounts).                                                                                                 |
| `total_tax`    | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                   |
| `taxes`        | array   | Line taxes. See [Purchase Order - Taxes properties](#purchase-order-taxes-properties) <i class="label label-info">read-only</i> |
| `meta_data`    | array   | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties)                                    |

### Purchase Order - Fee lines properties ###

| Attribute    | Type    | Description                                                                                                                   |
|--------------|---------|-------------------------------------------------------------------------------------------------------------------------------|
| `id`         | integer | Item ID. <i class="label label-info">read-only</i>                                                                            |
| `name`       | string  | Fee name.                                                                                                                     |
| `tax_class`  | string  | Tax class of fee.                                                                                                             |
| `tax_status` | string  | Tax status of fee. Options: `taxable` and `none`.                                                                             |
| `total`      | string  | Line total (after discounts).                                                                                                 |
| `total_tax`  | string  | Line total tax (after discounts). <i class="label label-info">read-only</i>                                                   |
| `taxes`      | array   | Line taxes. See [Purchase Order - Taxes properties](#purchase-order-taxes-properties) <i class="label label-info">read-only</i> |
| `meta_data`  | array   | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties)                                    |

### Purchase Order - Taxes properties ###

| Attribute            | Type    | Description                                                                                |
|----------------------|---------|--------------------------------------------------------------------------------------------|
| `id`                 | integer | Item ID. <i class="label label-info">read-only</i>                                         |
| `rate_code`          | string  | Tax rate code. <i class="label label-info">read-only</i>                                   |
| `rate_id`            | string  | Tax rate ID. <i class="label label-info">read-only</i>                                     |
| `label`              | string  | Tax rate label. <i class="label label-info">read-only</i>                                  |
| `compound`           | boolean | Show if is a compound tax rate. <i class="label label-info">read-only</i>                  |
| `tax_total`          | string  | Tax total (not including shipping taxes). <i class="label label-info">read-only</i>        |
| `shipping_tax_total` | string  | Shipping tax total. <i class="label label-info">read-only</i>                              |
| `meta_data`          | array   | Meta data. See [Purchase Order - Meta data properties](#purchase-order-meta-data-properties) |

### Purchase Order - MI Order Items properties <i class="label label-addon">Multi-Inventory</i> ###

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

### Purchase Order - BOM Order Items properties <i class="label label-addon">Product Levels</i> ###

| Attribute  | Type    | Description                                                                                                  |
|------------|---------|--------------------------------------------------------------------------------------------------------------|
| `id`       | integer | The BOM order item ID. <i class="label label-info">read-only</i>                                             |
| `bom_id`   | integer | The BOM product ID associated to the BOM order item.  <i class="label label-info">read-only</i>              |
| `bom_type` | string  | The BOM product type. Options: `product_part` and `raw_material`.  <i class="label label-info">read-only</i> |                                                                         |
| `qty`      | number  | The quantity of the specified BOM that is used on the order item.  <i class="label label-info">read-only</i> |                                                                                      |

## Create a purchase order ##

This API helps you to create a new purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders</h6>
	</div>
</div>

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/purchase-orders \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
  "supplier": 399,
  "date_expected": "2019-11-11T11:26:41",
  "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
  "status": "atum_ordered",
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
  ]
}'
```

```javascript
const data = {
   supplier: 399,
   date_expected: "2019-11-11T11:26:41",
   description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
   status: "atum_ordered",
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
   ]
};

WooCommerce.post("atum/purchase-orders", data)
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
  'supplier' => 399,
  'date_expected' => '2019-11-11T11:26:41',
  'description' => 'Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.',
  'status' => 'atum_ordered',
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
  ]
];

print_r($woocommerce->post('atum/purchase-orders', $data));
?>
```

```python
data = {
 "supplier": 399,
 "date_expected": "2019-11-11T11:26:41",
 "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
 "status": "atum_ordered",
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
 ]
}

print(wcapi.post("atum/purchase-orders", data).json())
```

```ruby
data = {
 supplier: 399,
 date_expected: "2019-11-11T11:26:41",
 description: "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
 status: "atum_ordered",
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
 ]
}

woocommerce.post("atum/purchase-orders", data).parsed_response
```

> JSON response example:

```json
{
    "id": 2156,
    "status": "atum_ordered",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-11-12T09:37:12",
    "date_modified": "2019-11-12T09:37:13",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "0.00",
    "shipping_tax": "0.00",
    "cart_tax": "1.20",
    "total": "13.20",
    "total_tax": "1.20",
    "date_completed": "2019-11-12T09:37:14",
    "line_items": [
        {
            "id": 337,
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
                    "id": 201,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 202,
                    "inventory_id": 126,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 203,
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
            "id": 338,
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
                    "id": "2872",
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
            "id": 339,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "1.20",
            "shipping_tax_total": "0.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [],
    "fee_lines": [],
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "supplier": "399",
    "multiple_suppliers": false,
    "date_expected": "2019-11-11T11:26:41",
    "date_created_gmt": "2019-11-12T08:37:12",
    "date_modified_gmt": "2019-11-12T09:37:13",
    "date_completed_gmt": "2019-11-12T08:37:14",
    "date_expected_gmt": "2019-11-11T10:26:41",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/2156"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
            }
        ]
    }
}
```

## Retrieve a purchase order ##

This API lets you retrieve and view a specific purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/purchase-orders/1841 \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/purchase-orders/1841")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/purchase-orders/1841')); ?>
```

```python
print(wcapi.get("atum/purchase-orders/1841").json())
```

```ruby
woocommerce.get("atum/purchase-orders/1841").parsed_response
```

> JSON response example:

```json
{
    "id": 1841,
    "status": "atum_receiving",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-10-04T09:35:00",
    "date_modified": "2019-10-15T11:36:18",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "0.00",
    "shipping_tax": "0.00",
    "cart_tax": "5.20",
    "total": "31.20",
    "total_tax": "5.20",
    "date_completed": "2019-11-12T09:42:58",
    "line_items": [
        {
            "id": 313,
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
            "meta_data": {               
                "18": {
                    "id": "2703",
                    "key": "final",
                    "value": "version"
                }
            },
            "sku": "Back Orders",
            "price": 3,
            "mi_inventories": [],
            "bom_items": []
        },
        {
            "id": 314,
            "name": "Ship Your Idea 2 - Black",
            "product_id": 22,
            "variation_id": 23,
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
                    "id": "2633",
                    "key": "pa_color",
                    "value": "black"
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
            "id": 315,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "5.20",
            "shipping_tax_total": "0.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [],
    "fee_lines": [],
    "description": "",
    "supplier": "399",
    "multiple_suppliers": false,
    "date_expected": "2019-10-05T08:00:00",
    "date_created_gmt": "2019-10-04T09:35:00",
    "date_modified_gmt": "2019-10-15T11:36:18",
    "date_completed_gmt": "2019-11-12T08:42:58",
    "date_expected_gmt": "2019-10-05T08:00:00",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/1841"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                       |
|-----------|--------|---------------------------------------------------|
| `dp`      | string | Number of decimal points to use in each resource. |

## List all purchase orders ##

This API helps you to view all the purchase orders.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/atum/purchase-orders \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("atum/purchase-orders")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('atum/purchase-orders')); ?>
```

```python
print(wcapi.get("atum/purchase-orders").json())
```

```ruby
woocommerce.get("atum/purchase-orders").parsed_response
```

> JSON response example:

```json
[
    {
        "id": 1927,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2019-10-24T10:16:12",
        "date_modified": "2019-10-24T10:16:13",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "20.00",
        "shipping_tax": "2.00",
        "cart_tax": "4.00",
        "total": "66.00",
        "total_tax": "6.00",
        "date_completed": "2019-11-12T09:45:21",
        "line_items": [
            {
                "id": 316,
                "name": "ABC 123 XPTO",
                "product_id": 507,
                "variation_id": 0,
                "quantity": 5,
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
                "meta_data": [],
                "sku": "",
                "price": 0,
                "mi_inventories": [
                    {
                        "id": 189,
                        "inventory_id": 152,
                        "qty": 3,
                        "subtotal": 60,
                        "total": 60,
                        "refund_qty": 0,
                        "refund_total": 0
                    },
                    {
                        "id": 190,
                        "inventory_id": 126,
                        "qty": 2,
                        "subtotal": 20,
                        "total": 20,
                        "refund_qty": 0,
                        "refund_total": 0
                    }
                ],
                "bom_items": []
            },
            {
                "id": 317,
                "name": "Ship Your Idea 2 - Black",
                "product_id": 22,
                "variation_id": 23,
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
                        "id": "2722",
                        "key": "pa_color",
                        "value": "black"
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
                "id": 319,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "4.00",
                "shipping_tax_total": "2.00",
                "meta_data": []
            }
        ],
        "shipping_lines": [
            {
                "id": 318,
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
        "description": "",
        "supplier": false,
        "multiple_suppliers": true,
        "date_expected": "2019-11-12T09:45:21",
        "date_created_gmt": "2019-10-24T08:16:12",
        "date_modified_gmt": "2019-10-24T10:16:13",
        "date_completed_gmt": "2019-11-12T08:45:21",
        "date_expected_gmt": "2019-11-12T08:45:21",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/1927"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                }
            ]
        }
    },
    {
        "id": 852,
        "status": "atum_received",
        "currency": "USD",
        "prices_include_tax": false,
        "date_created": "2019-04-30T18:35:00",
        "date_modified": "2019-10-03T12:01:16",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "10.00",
        "shipping_tax": "2.00",
        "cart_tax": "2.00",
        "total": "24.00",
        "total_tax": "4.00",
        "date_completed": "2019-11-12T09:45:21",
        "line_items": [
            {
                "id": 283,
                "name": "Variable Raw Material - Orange",
                "product_id": 639,
                "variation_id": 0,
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
                    "10": {
                        "id": "2337",
                        "key": "pa_color",
                        "value": "orange"
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
                "id": 287,
                "rate_code": "GB-VAT-1",
                "rate_id": 1,
                "label": "VAT",
                "compound": false,
                "tax_total": "2.00",
                "shipping_tax_total": "2.00",
                "meta_data": []
            }
        ],
        "shipping_lines": [
            {
                "id": 286,
                "method_title": "Flat rate",
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
        "fee_lines": [
            {
                "id": 288,
                "name": "Fee Edited",
                "tax_class": "",
                "tax_status": "taxable",
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
        "description": "",
        "supplier": false,
        "multiple_suppliers": true,
        "date_expected": "2019-04-30T16:35:00",
        "date_created_gmt": "2019-04-30T18:35:00",
        "date_modified_gmt": "2019-10-03T12:01:16",
        "date_completed_gmt": "2019-11-12T08:45:21",
        "date_expected_gmt": "2019-04-30T16:35:00",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/852"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                }
            ]
        }
    },
    {
        "id": 851,
        "status": "atum_received",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2019-04-30T17:40:00",
        "date_modified": "2019-04-30T17:48:14",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "0.00",
        "total": "0.00",
        "total_tax": "0.00",
        "date_completed": "2019-11-12T09:45:21",
        "line_items": [
            {
                "id": 282,
                "name": "Variable Raw Material - Orange",
                "product_id": 639,
                "variation_id": 0,
                "quantity": 2,
                "tax_class": "",
                "subtotal": "0.00",
                "subtotal_tax": "0.00",
                "total": "0.00",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": {
                    "9": {
                        "id": "2288",
                        "key": "pa_color",
                        "value": "orange"
                    }
                },
                "sku": "",
                "price": 0,
                "mi_inventories": [],
                "bom_items": []
            }
        ],
        "tax_lines": [],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "",
        "supplier": false,
        "multiple_suppliers": true,
        "date_expected": "2019-04-30T15:47:00",
        "date_created_gmt": "2019-04-30T17:40:00",
        "date_modified_gmt": "2019-04-30T17:48:14",
        "date_completed_gmt": "2019-11-12T08:45:21",
        "date_expected_gmt": "2019-04-30T15:47:00",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/851"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                }
            ]
        }
    },
    {
        "id": 843,
        "status": "atum_pending",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2019-04-30T13:17:00",
        "date_modified": "2019-09-10T12:26:12",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "0.00",
        "total": "14.10",
        "total_tax": "0.00",
        "date_completed": "2019-11-12T09:45:22",
        "line_items": [
            {
                "id": 278,
                "name": "Product Part 1",
                "product_id": 175,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "zero-rate",
                "subtotal": "12.00",
                "subtotal_tax": "0.00",
                "total": "12.00",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": [],
                "sku": "PART1",
                "price": 12,
                "mi_inventories": [],
                "bom_items": []
            },
            {
                "id": 279,
                "name": "Variable Product Part 1 - Black",
                "product_id": 512,
                "variation_id": 513,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "2.10",
                "subtotal_tax": "0.00",
                "total": "2.10",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": {
                    "9": {
                        "id": "2256",
                        "key": "pa_color",
                        "value": "black"
                    }
                },
                "sku": "VPART1",
                "price": 2.1,
                "mi_inventories": [],
                "bom_items": []
            }
        ],
        "tax_lines": [],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "",
        "supplier": false,
        "multiple_suppliers": true,
        "date_expected": "2019-04-30T11:20:00",
        "date_created_gmt": "2019-04-30T13:17:00",
        "date_modified_gmt": "2019-09-10T12:26:12",
        "date_completed_gmt": "2019-11-12T08:45:22",
        "date_expected_gmt": "2019-04-30T11:20:00",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/843"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                }
            ]
        }
    },   
    {
        "id": 797,
        "status": "atum_received",
        "currency": "EUR",
        "prices_include_tax": false,
        "date_created": "2019-04-23T08:33:00",
        "date_modified": "2019-05-27T09:16:09",
        "discount_total": "0.00",
        "discount_tax": "0.00",
        "shipping_total": "0.00",
        "shipping_tax": "0.00",
        "cart_tax": "0.00",
        "total": "4.00",
        "total_tax": "0.00",
        "date_completed": "2019-11-12T09:45:22",
        "line_items": [
            {
                "id": 274,
                "name": "ABC 123 XPTO",
                "product_id": 507,
                "variation_id": 0,
                "quantity": 1,
                "tax_class": "",
                "subtotal": "4.00",
                "subtotal_tax": "0.00",
                "total": "4.00",
                "total_tax": "0.00",
                "taxes": [],
                "meta_data": [],
                "sku": "",
                "price": 4,
                "mi_inventories": [],
                "bom_items": []
            }
        ],
        "tax_lines": [],
        "shipping_lines": [],
        "fee_lines": [],
        "description": "",
        "supplier": "426",
        "multiple_suppliers": false,
        "date_expected": "2019-06-28T00:00:00",
        "date_created_gmt": "2019-04-23T08:33:00",
        "date_modified_gmt": "2019-05-27T09:16:09",
        "date_completed_gmt": "2019-11-12T08:45:22",
        "date_expected_gmt": "2019-06-28T00:00:00",
        "_links": {
            "self": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/797"
                }
            ],
            "collection": [
                {
                    "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                }
            ]
        }
    }
]
```

#### Available parameters ####

| Parameter            | Type      | Description                                                                                                                                                                                        |
|----------------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `context`            | string    | Scope under which the request is made; determines fields present in response. Options: `view` and `edit`. Default is `view`.                                                                       |
| `page`               | integer   | Current page of the collection. Default is `1`.                                                                                                                                                    |
| `per_page`           | integer   | Maximum number of items to be returned in result set. Default is `10`.                                                                                                                             |
| `search`             | string    | Limit results to those matching a string.                                                                                                                                                          |
| `after`              | string    | Limit response to resources published after a given ISO8601 compliant date.                                                                                                                        |
| `before`             | string    | Limit response to resources published before a given ISO8601 compliant date.                                                                                                                       |
| `exclude`            | array     | Ensure result set excludes specific IDs.                                                                                                                                                           |
| `include`            | array     | Limit result set to specific ids.                                                                                                                                                                  |
| `offset`             | integer   | Offset the result set by a specific number of items.                                                                                                                                               |
| `order`              | string    | Order sort attribute ascending or descending. Options: `asc` and `desc`. Default is `desc`.                                                                                                        |
| `orderby`            | string    | Sort collection by object attribute. Options: `date`, `id`, `include`, `title` and `slug`. Default is `date`.                                                                                      |
| `parent`             | array     | Limit result set to those of particular parent IDs.                                                                                                                                                |
| `parent_exclude`     | array     | Limit result set to all items except those of a particular parent ID.                                                                                                                              |
| `status`             | array     | Limit result set to purchas orders assigned a specific status. Options: `any`, `atum_pending`, `atum_ordered`, `atum_onthewayin`, `atum_receiving`, `atum_received` and `trash`. Default is `any`. |
| `product`            | integer   | Limit result set to purchase orders assigned a specific product.                                                                                                                                   |
| `dp`                 | integer   | Number of decimal points to use in each resource. Default is `2`.                                                                                                                                  |
| `date_expected`      | date-time | Limit result set to purchase orders expected at location on a given ISO8601 compliant date.                                                                                                        |
| `supplier`           | integer   | Limit result set to purchase orders linked to the specified supplier ID.                                                                                                                           |
| `multiple_suppliers` | boolean   | Limit result set to purchase orders depending on their multiple_suppliers switch status.                                                                                                           |

## Update a purchase order ##

This API lets you make changes to a purchase order.

### HTTP Request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-put">PUT</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X PUT https://example.com/wp-json/wc/v3/atum/purchase-orders/1927 \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
          "status": "atum_received"
        }'
```

```javascript
const data = {
   status: "atum_received"
 };

WooCommerce.put("atum/purchase-orders/1927", data)
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
  'status' => 'atum_received'
];

print_r($woocommerce->put('atum/purchase-orders/1927', $data));
?>
```

```python
data = {
 "status": "atum_received"
}

print(wcapi.put("atum/purchase-orders/1927", data).json())
```

```ruby
data = {
 status: "atum_received"
}

woocommerce.put("atum/purchase-orders/1927", data).parsed_response
```

> JSON response example:

```json
{
    "id": 1927,
    "status": "atum_received",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-10-24T10:16:12",
    "date_modified": "2019-11-12T10:15:56",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "20.00",
    "shipping_tax": "2.00",
    "cart_tax": "4.00",
    "total": "66.00",
    "total_tax": "6.00",
    "date_completed": "2019-11-12T10:15:58",
    "line_items": [
        {
            "id": 316,
            "name": "ABC 123 XPTO",
            "product_id": 507,
            "variation_id": 0,
            "quantity": 5,
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
            "meta_data": [],
            "sku": "",
            "price": 0,
            "mi_inventories": [
                {
                    "id": 189,
                    "inventory_id": 152,
                    "qty": 3,
                    "subtotal": 60,
                    "total": 60,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 190,
                    "inventory_id": 126,
                    "qty": 2,
                    "subtotal": 20,
                    "total": 20,
                    "refund_qty": 0,
                    "refund_total": 0
                }
            ],
            "bom_items": [
                {
                    "bom_id": 183,
                    "bom_type": "raw_material",
                    "qty": 10
                },
                {
                    "bom_id": 184,
                    "bom_type": "product_part",
                    "qty": 5
                }
            ]
        },
        {
            "id": 317,
            "name": "Ship Your Idea 2 - Black",
            "product_id": 22,
            "variation_id": 23,
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
                    "id": "2722",
                    "key": "pa_color",
                    "value": "black"
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
            "id": 319,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "4.00",
            "shipping_tax_total": "2.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [
        {
            "id": 318,
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
    "description": "",
    "supplier": false,
    "multiple_suppliers": true,
    "date_expected": "2019-11-12T10:15:58",
    "date_created_gmt": "2019-10-24T08:16:12",
    "date_modified_gmt": "2019-11-12T10:15:56",
    "date_completed_gmt": "2019-11-12T09:15:58",
    "date_expected_gmt": "2019-11-12T09:15:58",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/1927"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
            }
        ]
    }
}
```

## Delete a purchase order ##

This API helps you delete a purchase order.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-delete">DELETE</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/&lt;id&gt;</h6>
	</div>
</div>

```shell
curl -X DELETE https://example.com/wp-json/wc/v3/atum/purchase-orders/2156?force=true \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.delete("atum/purchase-orders/2156", {
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
<?php print_r($woocommerce->delete('atum/purchase-orders/2156', ['force' => true])); ?>
```

```python
print(wcapi.delete("atum/purchase-orders/2156", params={"force": True}).json())
```

```ruby
woocommerce.delete("atum/purchase-orders/2156", force: true).parsed_response
```

> JSON response example:

```json
{
    "id": 2156,
    "status": "atum_ordered",
    "currency": "EUR",
    "prices_include_tax": false,
    "date_created": "2019-11-12T09:37:12",
    "date_modified": "2019-11-12T09:37:13",
    "discount_total": "0.00",
    "discount_tax": "0.00",
    "shipping_total": "0.00",
    "shipping_tax": "0.00",
    "cart_tax": "1.20",
    "total": "13.20",
    "total_tax": "1.20",
    "date_completed": "2019-11-12T10:18:43",
    "line_items": [
        {
            "id": 337,
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
                    "id": 201,
                    "inventory_id": 152,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 202,
                    "inventory_id": 126,
                    "qty": 1,
                    "subtotal": 3,
                    "total": 0,
                    "refund_qty": 0,
                    "refund_total": 0
                },
                {
                    "id": 203,
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
            "id": 338,
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
                    "id": "2872",
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
            "id": 339,
            "rate_code": "GB-VAT-1",
            "rate_id": 1,
            "label": "VAT",
            "compound": false,
            "tax_total": "1.20",
            "shipping_tax_total": "0.00",
            "meta_data": []
        }
    ],
    "shipping_lines": [],
    "fee_lines": [],
    "description": "Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Vestibulum tortor quam, feugiat vitae, ultricies eget, tempor sit amet, ante. Donec eu libero sit amet quam egestas semper. Aenean ultricies mi vitae est. Mauris placerat eleifend leo.",
    "supplier": "399",
    "multiple_suppliers": false,
    "date_expected": "2019-11-11T11:26:41",
    "date_created_gmt": "2019-11-12T08:37:12",
    "date_modified_gmt": "2019-11-12T09:37:13",
    "date_completed_gmt": "2019-11-12T09:18:43",
    "date_expected_gmt": "2019-11-11T10:26:41",
    "_links": {
        "self": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/2156"
            }
        ],
        "collection": [
            {
                "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
            }
        ]
    }
}
```

#### Available parameters ####

| Parameter | Type   | Description                                                                      |
|-----------|--------|----------------------------------------------------------------------------------|
| `force`   | string | Use `true` whether to permanently delete the purchase order, Default is `false`. |

## Batch update purchase orders ##

This API helps you to batch create, update and delete multiple purchase orders.

<aside class="notice">
Note: By default it's limited to up to 100 objects to be created, updated or deleted. 
</aside>

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/wp-json/wc/v3/atum/purchase-orders/batch</h6>
	</div>
</div>

> Example of Create, Update and Delete items in bulk:

```shell
curl -X POST https://example.com/wp-json/wc/v3/atum/purchase-orders/batch \
	-u consumer_key:consumer_secret \
	-H "Content-Type: application/json" \
	-d '{
      "create": [
        {
          "supplier": 399",
          "status": "atum_onthewayin",
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
          "multiple_suppliers": true,
          "status": "atum_pending",
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
          "id": 1841,         
          "date_expected": "2019-11-11T12:15:14"
        }
      ],
      "delete": [
        1927
      ]
    }'
```

```javascript
const data = {
   create: [
     {
       supplier: 399,
       status: "atum_onthewayin",
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
       multiple_suppliers: true,
       status: "atum_pending",
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
       id: 1841,       
       date_expected: "2019-11-11T12:15:14"
     }
   ],
   delete: [
     1927
   ]
};

WooCommerce.post("atum/purchase-orders/batch", data)
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
      'supplier' => 399,
      'status' => 'atum_onthewayin',
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
      'multiple_suppliers' => true,
      'status' => 'atum_pending',
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
      'id' => 1841,    
      'date_expected' => '2019-11-11T12:15:14'
    ]
  ],
  'delete' => [
    1927
  ]
];

print_r($woocommerce->post('atum/purchase-orders/batch', $data));
?>
```

```python
data = {
 "create": [
   {
     "supplier": 399,
     "status": "atum_onthewayin",
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
     "multiple_suppliers": true,
     "status": "atum_pending",
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
     "id": 1841,    
     "date_expected": "2019-11-11T12:15:14"
   }
 ],
 "delete": [
   1927
 ]
}

print(wcapi.post("atum/purchase-orders/batch", data).json())
```

```ruby
data = {
 create: [
   {
     supplier: 399,
     status: "atum_onthewayin",
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
     multiple_suppliers: true,
     status: "atum_pending",
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
     id: 1841,     
     date_expected: "2019-11-11T12:15:14"
   }
 ],
 delete: [
   1927
 ]
}

woocommerce.post("atum/purchase-orders/batch", data).parsed_response
```

> JSON response example:

```json
{
    "create": [
        {
            "id": 2157,
            "status": "atum_onthewayin",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-11-12T10:24:07",
            "date_modified": "2019-11-12T10:24:08",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "60.00",
            "shipping_tax": "6.00",
            "cart_tax": "3.60",
            "total": "105.60",
            "total_tax": "9.60",
            "date_completed": "2019-11-12T10:24:08",
            "line_items": [
                {
                    "id": 340,
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
                            "id": 204,
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
                    "id": 341,
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
                            "id": 205,
                            "inventory_id": 14,
                            "qty": 1,
                            "subtotal": 3,
                            "total": 0,
                            "refund_qty": 0,
                            "refund_total": 0
                        },
                        {
                            "id": 206,
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
                    "id": 342,
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
                            "id": "2905",
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
                    "id": 344,
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
                    "id": 343,
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
            "supplier": "399",
            "multiple_suppliers": false,
            "date_expected": "2019-11-12T10:24:08",
            "date_created_gmt": "2019-11-12T09:24:07",
            "date_modified_gmt": "2019-11-12T10:24:08",
            "date_completed_gmt": "2019-11-12T09:24:08",
            "date_expected_gmt": "2019-11-12T09:24:08",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/2157"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                    }
                ]
            }
        },
        {
            "id": 2158,
            "status": "atum_pending",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-11-12T10:24:09",
            "date_modified": "2019-11-12T10:24:11",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "40.00",
            "shipping_tax": "4.00",
            "cart_tax": "4.00",
            "total": "88.00",
            "total_tax": "8.00",
            "date_completed": "2019-11-12T10:24:11",
            "line_items": [
                {
                    "id": 345,
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
                            "id": "2924",
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
                    "id": 346,
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
                            "id": "2934",
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
                    "id": 348,
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
                    "id": 347,
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
            "supplier": false,
            "multiple_suppliers": true,
            "date_expected": "2019-11-12T10:24:12",
            "date_created_gmt": "2019-11-12T09:24:09",
            "date_modified_gmt": "2019-11-12T10:24:11",
            "date_completed_gmt": "2019-11-12T09:24:11",
            "date_expected_gmt": "2019-11-12T09:24:12",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/2158"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                    }
                ]
            }
        }
    ],
    "update": [
        {
            "id": 1841,
            "status": "atum_receiving",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-10-04T09:35:00",
            "date_modified": "2019-11-12T10:24:12",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "0.00",
            "shipping_tax": "0.00",
            "cart_tax": "5.20",
            "total": "31.20",
            "total_tax": "5.20",
            "date_completed": "2019-11-12T10:24:12",
            "line_items": [
                {
                    "id": 313,
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
                    "meta_data": {                     
                        "18": {
                            "id": "2703",
                            "key": "final",
                            "value": "version"
                        }
                    },
                    "sku": "Back Orders",
                    "price": 3,
                    "mi_inventories": [],
                    "bom_items": []
                },
                {
                    "id": 314,
                    "name": "Ship Your Idea 2 - Black",
                    "product_id": 22,
                    "variation_id": 23,
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
                            "id": "2633",
                            "key": "pa_color",
                            "value": "black"
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
                    "id": 315,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "5.20",
                    "shipping_tax_total": "0.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [],
            "fee_lines": [],
            "description": "",
            "supplier": "399",
            "multiple_suppliers": false,
            "date_expected": "2019-11-11T12:15:14",
            "date_created_gmt": "2019-10-04T09:35:00",
            "date_modified_gmt": "2019-11-12T10:24:12",
            "date_completed_gmt": "2019-11-12T09:24:12",
            "date_expected_gmt": "2019-11-11T11:15:14",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/1841"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                    }
                ]
            }
        }
    ],
    "delete": [
        {
            "id": 1927,
            "status": "atum_received",
            "currency": "EUR",
            "prices_include_tax": false,
            "date_created": "2019-10-24T10:16:12",
            "date_modified": "2019-11-12T10:15:56",
            "discount_total": "0.00",
            "discount_tax": "0.00",
            "shipping_total": "20.00",
            "shipping_tax": "2.00",
            "cart_tax": "4.00",
            "total": "66.00",
            "total_tax": "6.00",
            "date_completed": "2019-11-12T10:24:12",
            "line_items": [
                {
                    "id": 316,
                    "name": "ABC 123 XPTO",
                    "product_id": 507,
                    "variation_id": 0,
                    "quantity": 5,
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
                    "meta_data": [],
                    "sku": "",
                    "price": 0,
                    "mi_inventories": [
                        {
                            "id": 189,
                            "inventory_id": 152,
                            "qty": 3,
                            "subtotal": 60,
                            "total": 60,
                            "refund_qty": 0,
                            "refund_total": 0
                        },
                        {
                            "id": 190,
                            "inventory_id": 126,
                            "qty": 2,
                            "subtotal": 20,
                            "total": 20,
                            "refund_qty": 0,
                            "refund_total": 0
                        }
                    ],
                    "bom_items": [
                        {
                            "bom_id": 183,
                            "bom_type": "raw_material",
                            "qty": 10
                        },
                        {
                            "bom_id": 184,
                            "bom_type": "product_part",
                            "qty": 5
                        }
                    ]
                },
                {
                    "id": 317,
                    "name": "Ship Your Idea 2 - Black",
                    "product_id": 22,
                    "variation_id": 23,
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
                            "id": "2722",
                            "key": "pa_color",
                            "value": "black"
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
                    "id": 319,
                    "rate_code": "GB-VAT-1",
                    "rate_id": 1,
                    "label": "VAT",
                    "compound": false,
                    "tax_total": "4.00",
                    "shipping_tax_total": "2.00",
                    "meta_data": []
                }
            ],
            "shipping_lines": [
                {
                    "id": 318,
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
            "description": "",
            "supplier": false,
            "multiple_suppliers": true,
            "date_expected": "2019-11-12T10:24:12",
            "date_created_gmt": "2019-10-24T08:16:12",
            "date_modified_gmt": "2019-11-12T10:15:56",
            "date_completed_gmt": "2019-11-12T09:24:12",
            "date_expected_gmt": "2019-11-12T09:24:12",
            "_links": {
                "self": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders/1927"
                    }
                ],
                "collection": [
                    {
                        "href": "https://example.com/wp-json/wc/v3/atum/purchase-orders"
                    }
                ]
            }
        }
    ]
}
```
