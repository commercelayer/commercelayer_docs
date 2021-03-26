---
description: The carrier account object and its fields
---

# Carrier accounts

## The carrier account object

A **carrier account** object is returned as part of the response body of each successful list or retrieve API call.

| Field | Type | Description |
| :--- | :--- | :--- |
| **type** | `string` | `carrier_accounts` |
| **id** | `string` | The carrier account unique identifier |
| links.**self** | `string` | The carrier account endpoint URL |
| attributes.**name** | `string` | The carrier account internal name. |
| attributes.**easypost\_type** | `string` | The Easypost service carrier type. |
| attributes.**easypost\_id** | `string` | The Easypost internal reference ID. |
| attributes.**credentials** | `object` | The Easypost carrier accounts credentials fields. |
| attributes.**created\_at** | `datetime` | Time at which the resource was created. |
| attributes.**updated\_at** | `datetime` | Time at which the resource was last updated. |
| attributes.**reference** | `string` | A string that you can use to add any external identifier to the resource. This can be useful for integrating the resource to an external system, like an ERP, a marketing tool, a CRM, or whatever. |
| attributes.**reference\_origin** | `string` | Any identifier of the third party system that defines the reference code |
| attributes.**metadata** | `object` | Set of key-value pairs that you can attach to the resource. This can be useful for storing additional information about the resource in a structured format. |
| relationships.**market** | `object` | The associated market. |
| relationships.**attachments** | `array` | The associated attachments. |
| meta.**mode** | `string` | The resource environment \(can be one of `test` or `live`\) |
