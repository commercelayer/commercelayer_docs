---
description: How to create A merchant via API
---

# Create A merchant

To create a new merchant, send a `POST` request to the `/api/merchants` endpoint, passing the resource arguments in the request body.

{% page-ref page="../../creating-resources.md" %}

## Request

**POST** https://yourdomain.commercelayer.io**/api/merchants**

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
| relationships.**address** | `has_one` | required |

### Example

{% tabs %}
{% tab title="Request" %}
The following request creates a new merchant:

```javascript
curl -X POST \
  https://yourdomain.commercelayer.io/api/merchants \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token' \
  -H 'Content-Type: application/vnd.api+json' \
  -d '{
  "data": {
    "type": "merchants",
    "attributes": {
      "name": "The Brand Inc."
    },
    "relationships": {
      "address": {
        "data": {
          "type": "addresses",
          "id": "zxcVBnMASd"
        }
      }
    }
  }
}'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `201 Created` status code, returning the created `merchant` object:

```javascript
{
  "data": {
    "id": "xYZkjABcde",
    "type": "merchants",
    "links": {
        "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde"
    },
    "attributes": {
        "name": "The Brand Inc."
        "created_at": "2018-01-01T12:00:00.000Z"
        "updated_at": "2018-01-01T12:00:00.000Z"
        "reference": "ANYREFEFERNCE"
        "metadata": "{:foo=>"bar"}"
    },
    "relationships": {
        "address": {
          "links": {
              "self": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/relationships/address",
              "related": "https://yourdomain.commercelayer.io/api/merchants/xYZkjABcde/address"
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