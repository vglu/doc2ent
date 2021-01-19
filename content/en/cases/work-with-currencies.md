---
title: "Works with Currencies"
date: 2021-01-13
tags:
  - Currency
tables:
  - Currency
Entities: 
  - CurrencyEntity
AXPath: Cost accounting\Ledger setup\Currencies
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

| Data entity AOT name | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category  | ReadOnly |
| -------------------- | ----------------- | ------------------------------ | ------------- | ----------- | --------- | -------- |
| CurrencyEntity       | Currencies        | Currencies                     | Yes           | Yes         | Reference | No       |

`CurrencyEntity` Entity is allowed to operate with warehowses in D365FO.

## Key

- CurrencyCode

## Fields

| Field name                           | Value example | Description |
| ------------------------------------ | ------------- | ----------- |
| (*)**CurrencyCode**                  | "USD"         |             |
| RoundingMethodPurchaseOrders         | "Ordinary"    |             |
| RoundingMethodPrices                 | "Ordinary"    |             |
| Name                                 | "US Dollar"   |             |
| RoundingMethodSalesOrders            | "Ordinary"    |             |
| Symbol                               | "$"           |             |
| RoundingRuleFixedAssetDepreciation   | 0             |             |
| ReferenceCurrencyForTriangulation    | "No"          |             |
| CurrencyGender                       | "Male"        |             |
| RoundingRulePurchaseOrders           | 0             |             |
| GeneralRoundingRule                  | 0             |             |
| RoundingMethodFixedAssetDepreciation | "Ordinary"    |             |
| RoundingRulePrices                   | 0             |             |
| RoundingRuleSalesOrders              | 0             |             |
| DecimalsCount_MX                     | 0             |             |


## Postman

### Request for get data

`GET: https://{{base_url}}/data/Currencies(CurrencyCode='USD')`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#Currencies/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE0NDczMDswLDU2MzcxNDQ3MzAn\"",
    "CurrencyCode": "USD",
    "RoundingMethodPurchaseOrders": "Ordinary",
    "RoundingMethodPrices": "Ordinary",
    "Name": "US Dollar",
    "RoundingMethodSalesOrders": "Ordinary",
    "Symbol": "$",
    "RoundingRuleFixedAssetDepreciation": 0,
    "ReferenceCurrencyForTriangulation": "No",
    "CurrencyGender": "Male",
    "RoundingRulePurchaseOrders": 0,
    "GeneralRoundingRule": 0,
    "RoundingMethodFixedAssetDepreciation": "Ordinary",
    "RoundingRulePrices": 0,
    "RoundingRuleSalesOrders": 0,
    "DecimalsCount_MX": 0
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/Currencies`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Currency",
    "CurrencyCode": "AFN"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#Currencies/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE0NDU3NzswLDU2MzcxNDQ1Nzcn\"",
    "CurrencyCode": "AFN",
    "RoundingMethodPurchaseOrders": "Ordinary",
    "RoundingMethodPrices": "Ordinary",
    "Name": "Afghani",
    "RoundingMethodSalesOrders": "Ordinary",
    "Symbol": "",
    "RoundingRuleFixedAssetDepreciation": 0,
    "ReferenceCurrencyForTriangulation": "No",
    "CurrencyGender": "Male",
    "RoundingRulePurchaseOrders": 0,
    "GeneralRoundingRule": 0,
    "RoundingMethodFixedAssetDepreciation": "Ordinary",
    "RoundingRulePrices": 0,
    "RoundingRuleSalesOrders": 0,
    "DecimalsCount_MX": 0
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/Currencies(CurrencyCode='AFN')`

<details>
    <summary>
    Header:
    </summary>

```json
    OData-Version:4.0
    OData-MaxVersion:4.0
    Content-Type:application/json;odata.metadata=minimal
    Accept:application/json;odata.metadata=minimal
    Accept-Charset:UTF-8
    Authorization:Bearer {{token}}
    Host:{{base_url}}
```

</details>

<details>
    <summary>
    body:
    </summary>

```json
{
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Currency",
    "Symbol": "&"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>
    Status: 204
</details>

### Request for delete data

`DELETE : https://{{base_url}}/data/Currencies(CurrencyCode='AFN')`

<details>
    <summary>
    Header:
    </summary>

```json
OData-Version:4.0
OData-MaxVersion:4.0
Content-Type:application/json;odata.metadata=minimal
Accept:application/json;odata.metadata=minimal
Accept-Charset:UTF-8
Authorization:Bearer {{token}}
Host:{{base_url}}
```

</details>

<details>
<summary>
Response:
</summary>
Status: 204
</details>
