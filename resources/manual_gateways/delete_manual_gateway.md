---
description: How to delete an existing manual gateway via API
---

# Delete a manual gateway

To delete a manual gateway, send a `DELETE` request to the `/api/manual_gateways/:id` endpoint, where `id` is the id of the manual gateway that you want to delete.

{% page-ref page="../../deleting-resources.md" %}

## Request

**DELETE** https://<i></i>yourdomain.commercelayer.io**/api/manual_gateways/:id**

### Example

{% tabs %}
{% tab title="Request" %}
The following request tries to delete the manual gateway identified by the ID "xYZkjABcde":

```javascript
curl -X DELETE \
  https://yourdomain.commercelayer.io/api/manual_gateways/xYZkjABcde \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer your-access-token'
```
{% endtab %}

{% tab title="Response" %}
On success, the API responds with a `204 No Content` status code.
{% endtab %}
{% endtabs %}

