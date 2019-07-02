---
description: How to create A customer group via API
---

# Create A customer group

To create a new customer group, send a `POST` request to the `/api/customer_groups` endpoint, passing the resource arguments in the request body.

{% page-ref page="../../creating-resources.md" %}

## Request

**POST** https://yourdomain.commercelayer.io**/api/customer_groups**

### Arguments

| Body Parameter | Type | Required |
| :--- | :--- | :--- |
| **type** | `string` | Required |
| attributes.**name** | `string` | required |
| attributes.**id** | `string` | required |
| attributes.**created_at** | `datetime` | required |
| attributes.**updated_at** | `datetime` | required |
| attributes.**reference** | `string` | optional |
| attributes.**metadata** | `object` | optional |
| relationships.**price_list** | `has_one` | optional |
| relationships.**customers** | `has_many` |  |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new customer group:

```javascript
curl -X POST \
  https://yourdomain.commercelayer.io/api/customer_groups \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "customer_groups",
    "attributes": {
      "name": ""
    },
    "relationships": {
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created `customer group` object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "customer_groups",
    "links": {
        "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde"
    },
    "attributes": {
        "name": ""
        "created_at": "2018-01-01T12:00:00.000Z"
        "updated_at": "2018-01-01T12:00:00.000Z"
        "reference": "ANYREFEFERNCE"
        "metadata": "{:foo=>"bar"}"
    },
    "relationships": {
        "price_list": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/price_list",
              "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/price_list"
          }
        }
        "customers": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/relationships/customers",
              "related": "https://yourdomain.commercelayer.io/api/customer_groups/xYZkjABcde/customers"
          }
        }
      },
      "meta": {
          "mode": "test"
      }
  }
}
```
{% endtab %}
{% endtabs %}