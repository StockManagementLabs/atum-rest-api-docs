# System status #

The system status API allows you to view all system status items.

## System status properties ##

| Attribute        | Type   | Description                                                                                                                                |
| ---------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `environment`    | object | Environment. See [System status - Environment properties](#system-status-environment-properties) <i class="label label-info">read-only</i> |
| `database`       | object | Database. See [System status - Database properties](#system-status-database-properties) <i class="label label-info">read-only</i>          |
| `active_plugins` | array  | Active plugins. <i class="label label-info">read-only</i>                                                                                  |
| `theme`          | object | Theme. See [System status - Theme properties](#system-status-theme-properties) <i class="label label-info">read-only</i>                   |
| `settings`       | object | Settings. See [System status - Settings properties](#system-status-settings-properties) <i class="label label-info">read-only</i>          |
| `security`       | object | Security. See [System status - Security properties](#system-status-security-properties) <i class="label label-info">read-only</i>          |
| `pages`          | array  | WooCommerce pages. <i class="label label-info">read-only</i>                                                                               |

### System status - Environment properties ###

| Attribute                   | Type    | Description                                                                |
| --------------------------- | ------- | -------------------------------------------------------------------------- |
| `home_url`                  | string  | Home URL. <i class="label label-info">read-only</i>                        |
| `site_url`                  | string  | Site URL. <i class="label label-info">read-only</i>                        |
| `wc_version`                | string  | WooCommerce version. <i class="label label-info">read-only</i>             |
| `log_directory`             | string  | Log directory. <i class="label label-info">read-only</i>                   |
| `log_directory_writable`    | boolean | Is log directory writable? <i class="label label-info">read-only</i>       |
| `wp_version`                | string  | WordPress version. <i class="label label-info">read-only</i>               |
| `wp_multisite`              | boolean | Is WordPress multisite? <i class="label label-info">read-only</i>          |
| `wp_memory_limit`           | integer | WordPress memory limit. <i class="label label-info">read-only</i>          |
| `wp_debug_mode`             | boolean | Is WordPress debug mode active? <i class="label label-info">read-only</i>  |
| `wp_cron`                   | boolean | Are WordPress cron jobs enabled? <i class="label label-info">read-only</i> |
| `language`                  | string  | WordPress language. <i class="label label-info">read-only</i>              |
| `server_info`               | string  | Server info. <i class="label label-info">read-only</i>                     |
| `php_version`               | string  | PHP version. <i class="label label-info">read-only</i>                     |
| `php_post_max_size`         | integer | PHP post max size. <i class="label label-info">read-only</i>               |
| `php_max_execution_time`    | integer | PHP max execution time. <i class="label label-info">read-only</i>          |
| `php_max_input_vars`        | integer | PHP max input vars. <i class="label label-info">read-only</i>              |
| `curl_version`              | string  | cURL version. <i class="label label-info">read-only</i>                    |
| `suhosin_installed`         | boolean | Is SUHOSIN installed? <i class="label label-info">read-only</i>            |
| `max_upload_size`           | integer | Max upload size. <i class="label label-info">read-only</i>                 |
| `mysql_version`             | string  | MySQL version. <i class="label label-info">read-only</i>                   |
| `default_timezone`          | string  | Default timezone. <i class="label label-info">read-only</i>                |
| `fsockopen_or_curl_enabled` | boolean | Is fsockopen/cURL enabled? <i class="label label-info">read-only</i>       |
| `soapclient_enabled`        | boolean | Is SoapClient class enabled? <i class="label label-info">read-only</i>     |
| `domdocument_enabled`       | boolean | Is DomDocument class enabled? <i class="label label-info">read-only</i>    |
| `gzip_enabled`              | boolean | Is GZip enabled? <i class="label label-info">read-only</i>                 |
| `mbstring_enabled`          | boolean | Is mbstring enabled? <i class="label label-info">read-only</i>             |
| `remote_post_successful`    | boolean | Remote POST successful? <i class="label label-info">read-only</i>          |
| `remote_post_response`      | string  | Remote POST response. <i class="label label-info">read-only</i>            |
| `remote_get_successful`     | boolean | Remote GET successful? <i class="label label-info">read-only</i>           |
| `remote_get_response`       | string  | Remote GET response. <i class="label label-info">read-only</i>             |

### System status - Database properties ###

| Attribute                | Type   | Description                                                       |
| ------------------------ | ------ | ----------------------------------------------------------------- |
| `wc_database_version`    | string | WC database version. <i class="label label-info">read-only</i>    |
| `database_prefix`        | string | Database prefix. <i class="label label-info">read-only</i>        |
| `maxmind_geoip_database` | string | MaxMind GeoIP database. <i class="label label-info">read-only</i> |
| `database_tables`        | array  | Database tables. <i class="label label-info">read-only</i>        |

### System status - Theme properties ###

| Attribute                 | Type    | Description                                                                           |
| ------------------------- | ------- | ------------------------------------------------------------------------------------- |
| `name`                    | string  | Theme name. <i class="label label-info">read-only</i>                                 |
| `version`                 | string  | Theme version. <i class="label label-info">read-only</i>                              |
| `version_latest`          | string  | Latest version of theme. <i class="label label-info">read-only</i>                    |
| `author_url`              | string  | Theme author URL. <i class="label label-info">read-only</i>                           |
| `is_child_theme`          | boolean | Is this theme a child theme? <i class="label label-info">read-only</i>                |
| `has_woocommerce_support` | boolean | Does the theme declare WooCommerce support? <i class="label label-info">read-only</i> |
| `has_woocommerce_file`    | boolean | Does the theme have a woocommerce.php file? <i class="label label-info">read-only</i> |
| `has_outdated_templates`  | boolean | Does this theme have outdated templates? <i class="label label-info">read-only</i>    |
| `overrides`               | array   | Template overrides. <i class="label label-info">read-only</i>                         |
| `parent_name`             | string  | Parent theme name. <i class="label label-info">read-only</i>                          |
| `parent_version`          | string  | Parent theme version. <i class="label label-info">read-only</i>                       |
| `parent_author_url`       | string  | Parent theme author URL. <i class="label label-info">read-only</i>                    |

### System status - Settings properties ###

| Attribute             | Type    | Description                                                                          |
| --------------------- | ------- | ------------------------------------------------------------------------------------ |
| `api_enabled`         | boolean | REST API enabled? <i class="label label-info">read-only</i>                          |
| `force_ssl`           | boolean | SSL forced? <i class="label label-info">read-only</i>                                |
| `currency`            | string  | Currency. <i class="label label-info">read-only</i>                                  |
| `currency_symbol`     | string  | Currency symbol. <i class="label label-info">read-only</i>                           |
| `currency_position`   | string  | Currency position. <i class="label label-info">read-only</i>                         |
| `thousand_separator`  | string  | Thousand separator. <i class="label label-info">read-only</i>                        |
| `decimal_separator`   | string  | Decimal separator. <i class="label label-info">read-only</i>                         |
| `number_of_decimals`  | integer | Number of decimals. <i class="label label-info">read-only</i>                        |
| `geolocation_enabled` | boolean | Geolocation enabled? <i class="label label-info">read-only</i>                       |
| `taxonomies`          | array   | Taxonomy terms for product/order statuses. <i class="label label-info">read-only</i> |

### System status - Security properties ###

| Attribute           | Type    | Description                                                                       |
| ------------------- | ------- | --------------------------------------------------------------------------------- |
| `secure_connection` | boolean | Is the connection to your store secure? <i class="label label-info">read-only</i> |
| `hide_errors`       | boolean | Hide errors from visitors? <i class="label label-info">read-only</i>              |

## List all system status items ##

This API helps you to view all the system status items.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-get">GET</i>
		<h6>/wp-json/wc/v3/system_status</h6>
	</div>
</div>

```shell
curl https://example.com/wp-json/wc/v3/system_status \
	-u consumer_key:consumer_secret
```

```javascript
WooCommerce.get("system_status")
  .then((response) => {
    console.log(response.data);
  })
  .catch((error) => {
    console.log(error.response.data);
  });
```

```php
<?php print_r($woocommerce->get('system_status')); ?>
```

```python
print(wcapi.get("system_status").json())
```

```ruby
woocommerce.get("system_status").parsed_response
```

> JSON response example:

```json
{
  "environment": {
    "home_url": "http://example.com",
    "site_url": "http://example.com",
    "version": "3.0.0",
    "log_directory": "/var/www/woocommerce/wp-content/uploads/wc-logs/",
    "log_directory_writable": true,
    "wp_version": "4.7.3",
    "wp_multisite": false,
    "wp_memory_limit": 134217728,
    "wp_debug_mode": true,
    "wp_cron": true,
    "language": "en_US",
    "server_info": "Apache/2.4.18 (Ubuntu)",
    "php_version": "7.1.3-2+deb.sury.org~yakkety+1",
    "php_post_max_size": 8388608,
    "php_max_execution_time": 30,
    "php_max_input_vars": 1000,
    "curl_version": "7.50.1, OpenSSL/1.0.2g",
    "suhosin_installed": false,
    "max_upload_size": 2097152,
    "mysql_version": "5.7.17",
    "default_timezone": "UTC",
    "fsockopen_or_curl_enabled": true,
    "soapclient_enabled": true,
    "domdocument_enabled": true,
    "gzip_enabled": true,
    "mbstring_enabled": true,
    "remote_post_successful": true,
    "remote_post_response": "200",
    "remote_get_successful": true,
    "remote_get_response": "200"
  },
  "database": {
    "wc_database_version": "3.0.0",
    "database_prefix": "wp_",
    "maxmind_geoip_database": "/var/www/woocommerce/wp-content/uploads/GeoIP.dat",
    "database_tables": {
      "woocommerce_sessions": true,
      "woocommerce_api_keys": true,
      "woocommerce_attribute_taxonomies": true,
      "woocommerce_downloadable_product_permissions": true,
      "woocommerce_order_items": true,
      "woocommerce_order_itemmeta": true,
      "woocommerce_tax_rates": true,
      "woocommerce_tax_rate_locations": true,
      "woocommerce_shipping_zones": true,
      "woocommerce_shipping_zone_locations": true,
      "woocommerce_shipping_zone_methods": true,
      "woocommerce_payment_tokens": true,
      "woocommerce_payment_tokenmeta": true
    }
  },
  "active_plugins": [
    {
      "plugin": "woocommerce/woocommerce.php",
      "name": "WooCommerce",
      "version": "3.0.0-rc.1",
      "version_latest": "2.6.14",
      "url": "https://woocommerce.com/",
      "author_name": "Automattic",
      "author_url": "https://woocommerce.com",
      "network_activated": false
    }
  ],
  "theme": {
    "name": "Twenty Sixteen",
    "version": "1.3",
    "version_latest": "1.3",
    "author_url": "https://wordpress.org/",
    "is_child_theme": false,
    "has_woocommerce_support": true,
    "has_woocommerce_file": false,
    "has_outdated_templates": false,
    "overrides": [],
    "parent_name": "",
    "parent_version": "",
    "parent_version_latest": "",
    "parent_author_url": ""
  },
  "settings": {
    "api_enabled": true,
    "force_ssl": false,
    "currency": "USD",
    "currency_symbol": "&#36;",
    "currency_position": "left",
    "thousand_separator": ",",
    "decimal_separator": ".",
    "number_of_decimals": 2,
    "geolocation_enabled": false,
    "taxonomies": {
      "external": "external",
      "grouped": "grouped",
      "simple": "simple",
      "variable": "variable"
    }
  },
  "security": {
    "secure_connection": true,
    "hide_errors": true
  },
  "pages": [
    {
      "page_name": "Shop base",
      "page_id": "4",
      "page_set": true,
      "page_exists": true,
      "page_visible": true,
      "shortcode": "",
      "shortcode_required": false,
      "shortcode_present": false
    },
    {
      "page_name": "Cart",
      "page_id": "5",
      "page_set": true,
      "page_exists": true,
      "page_visible": true,
      "shortcode": "[woocommerce_cart]",
      "shortcode_required": true,
      "shortcode_present": true
    },
    {
      "page_name": "Checkout",
      "page_id": "6",
      "page_set": true,
      "page_exists": true,
      "page_visible": true,
      "shortcode": "[woocommerce_checkout]",
      "shortcode_required": true,
      "shortcode_present": true
    },
    {
      "page_name": "My account",
      "page_id": "7",
      "page_set": true,
      "page_exists": true,
      "page_visible": true,
      "shortcode": "[woocommerce_my_account]",
      "shortcode_required": true,
      "shortcode_present": true
    }
  ]
}
```
