---
description: How to fetch a list of orders via API
---

# List all orders

To fetch a collection of orders, send a `GET` request to the `/api/orders` endpoint.

{% page-ref page="../../fetching-resources.md" %}

## Request

**GET** https://yourdomain.commercelayer.io**/api/orders**

### **Example**

The following request fetches a collection of orders:

```javascript
curl -X GET \
  https://yourdomain.commercelayer.io/api/orders/ \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```

On success, the API responds with a `200 OK` status code, returning a paginated collection of resource objects:

```javascript
{
  "data": [
    {
      "id": "xYZkjABcde",
      "type": "orders",
      "links": {
        "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde"
      },
      "attributes": {
        "number": "1234"
        "status": "draft"
        "payment_status": "unpaid"
        "fulfillment_status": "unfulfilled"
        "guest": "true"
        "editable": "true"
        "placeable": "false"
        "customer_email": "john@example.com"
        "language_code": "it"
        "currency_code": "EUR"
        "tax_included": "true"
        "tax_rate": "0.22"
        "freight_taxable": "true"
        "country_code": "IT"
        "shipping_country_code_lock": "IT"
        "coupon_code": "SUMMERDISCOUNT"
        "subtotal_amount_cents": "5000"
        "subtotal_amount_float": "50.0"
        "formatted_subtotal_amount": "€50,00"
        "shipping_amount_cents": "1200"
        "shipping_amount_float": "12.0"
        "formatted_shipping_amount": "€12,00"
        "payment_method_amount_cents": "0"
        "payment_method_amount_float": "0.0"
        "formatted_payment_method_amount": "€0,00"
        "discount_amount_cents": "-500"
        "discount_amount_float": "-5.0"
        "formatted_discount_amount": "-€5,00"
        "total_tax_amount_cents": "1028"
        "total_tax_amount_float": "10.28"
        "formatted_total_tax_amount": "€10,28"
        "subtotal_tax_amount_cents": "902"
        "subtotal_tax_amount_float": "9.02"
        "formatted_subtotal_tax_amount": "€9,02"
        "shipping_tax_amount_cents": "216"
        "shipping_tax_amount_float": "2.16"
        "formatted_shipping_tax_amount": "€2,16"
        "payment_method_tax_amount_cents": "0"
        "payment_method_tax_amount_float": "0.0"
        "formatted_payment_method_tax_amount": "€0,00"
        "discount_tax_amount_cents": "-90"
        "discount_tax_amount_float": "-0.9"
        "formatted_discount_tax_amount": "-€0,90"
        "total_amount_cents": "5700"
        "total_amount_float": "57.0"
        "formatted_total_amount": "€57,00"
        "total_taxable_amount_cents": "4672"
        "total_taxable_amount_float": "46.72"
        "formatted_total_taxable_amount": "€46,72"
        "subtotal_taxable_amount_cents": "4098"
        "subtotal_taxable_amount_float": "40.98"
        "formatted_subtotal_taxable_amount": "€40,98"
        "shipping_taxable_amount_cents": "984"
        "shipping_taxable_amount_float": "9.84"
        "formatted_shipping_taxable_amount": "€9,84"
        "payment_method_taxable_amount_cents": "0"
        "payment_method_taxable_amount_float": "0.0"
        "formatted_payment_method_taxable_amount": "€0,00"
        "discount_taxable_amount_cents": "-410"
        "discount_taxable_amount_float": "-4.10"
        "formatted_discount_taxable_amount": "-€4,10"
        "total_amount_with_taxes_cents": "5700"
        "total_amount_with_taxes_float": "57.00"
        "formatted_total_amount_with_taxes": "€57,00"
        "fees_amount_cents": "0"
        "fees_amount_float": "0.0"
        "formatted_fees_amount": "€0,00"
        "skus_count": "2"
        "line_item_options_count": "1"
        "shipments_count": "1"
        "payment_source_details": ""
        "token": "1c0994cc4e996e8c6ee56a2198f66f3c"
        "cart_url": "https://yourbrand.com/cart"
        "return_url": "https://yourbrand.com/"
        "terms_url": "https://yourbrand.com/terms"
        "privacy_url": "https://yourbrand.com/privacy"
        "checkout_url": "https://commerce.yourbrand.com/checkout/1c0994cc4e996e8c6ee56a2198f66f3c"
        "placed_at": "2018-01-01T12:00:00.000Z"
        "approved_at": "2018-01-01T12:00:00.000Z"
        "cancelled_at": "2018-01-01T12:00:00.000Z"
        "payment_updated_at": "2018-01-01T12:00:00.000Z"
        "fulfillment_updated_at": "2018-01-01T12:00:00.000Z"
        "created_at": "2018-01-01T12:00:00.000Z"
        "updated_at": "2018-01-01T12:00:00.000Z"
        "reference": "ANYREFEFERNCE"
        "metadata": "{:foo=>"bar"}"
      },
      "relationships": {
        "market": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/market",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/market"
          }
        }
        "customer": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/customer",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/customer"
          }
        }
        "shipping_address": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/shipping_address",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/shipping_address"
          }
        }
        "billing_address": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/billing_address",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/billing_address"
          }
        }
        "available_payment_methods": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/available_payment_methods",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/available_payment_methods"
          }
        }
        "payment_method": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/payment_method",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/payment_method"
          }
        }
        "payment_source": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/payment_source",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/payment_source"
          }
        }
        "line_items": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/line_items",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/line_items"
          }
        }
        "shipments": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/relationships/shipments",
              "related": "https://yourdomain.commercelayer.io/api/orders/xYZkjABcde/shipments"
          }
        }
      },
      "meta": {
        "mode": "test"
      }
    },
    {
      "other": "... 9 orders (first page)"
    }
  ],
  "meta": {
    "record_count": 140,
    "page_count": 14
  },
  "links": {
    "first": "https://yourdomain.commercelayer.io/api/orders?page[number]=1&page[size]=10",
    "next": "https://yourdomain.commercelayer.io/api/orders?page[number]=2&page[size]=10",
    "last": "https://yourdomain.commercelayer.io/api/orders?page[number]=14&page[size]=10"
  }
}
```

{% page-ref page="../../pagination.md" %}

### Sortable attributes

The list of orders can be sorted by the following attributes:

* `status`
* `payment_status`
* `fulfillment_status`
* `placed_at`
* `approved_at`
* `cancelled_at`
* `payment_updated_at`
* `fulfillment_updated_at`
* `id`
* `created_at`
* `updated_at`
* `reference`

{% page-ref page="../../sorting-results.md" %}
