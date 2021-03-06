---
description: The promotion object and its fields
---

# Promotions

Commerce Layer provides a promotional engine built on top of two main resources: promotions and [promotion rules](https://docs.commercelayer.io/api/resources/promotion_rules). Promotions are defined by market and — when triggered — are responsible for adding a specific discount to the market orders, based on their type. Within the time window given by their activation and expiration dates, promotions that have not reached their total usage limit are considered active. If no promotion rule is associated with an active promotion, the related discount is applied to all the orders of the market in scope. Otherwise, if one or more promotion rules are defined, the promotion is triggered only when it matches all of them. 

At the moment [fixed amount](https://docs.commercelayer.io/api/resources/fixed_amount_promotions), [free shipping](https://docs.commercelayer.io/api/resources/free_shipping_promotions), and [percentage discount](https://docs.commercelayer.io/api/resources/percentage_discount_promotions) are available (more to come). For any other cases, evaluate the option to leverage [external promotions](https://docs.commercelayer.io/api/resources/external_promotions).

The number of promotions that can be activated for a single market is subject to limitations: only **a maximum of 10 active promotions per market** is allowed, regardless of their type.

### The promotion object

A **promotion** object is returned as part of the response body of each successful list API call.

| Field | Type | Description |
| :--- | :--- | :--- |
| **type** | `string` | `promotions` |
| **id** | `string` | The promotion unique identifier |
| links.**self** | `string` | The promotion endpoint URL |
| attributes.**name** | `string` | The promotion's internal name. |
| attributes.**starts_at** | `datetime` | The activation date/time of this promotion. |
| attributes.**expires_at** | `datetime` | The expiration date/time of this promotion (must be after starts_at). |
| attributes.**total_usage_limit** | `integer` | The total number of times this promotion can be applied. |
| attributes.**total_usage_count** | `integer` | The number of times this promotion has been applied. |
| attributes.**active** | `boolean` | Indicates if the promotion is active. |
| attributes.**created_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**market** | `object` | The associated market. |
| relationships.**promotion_rules** | `array` | The associated promotion rules. |
| relationships.**order_amount_promotion_rule** | `object` | The associated order amount promotion rule. |
| relationships.**sku_list_promotion_rule** | `object` | The associated sku list promotion rule. |
| relationships.**coupon_codes_promotion_rule** | `object` | The associated coupon codes promotion rule. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |

