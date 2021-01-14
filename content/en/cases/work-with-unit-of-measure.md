---
title: "Works with Units (Unit of measure)"
date: 2021-01-13
type: docs
tags:
  - UnitOfMeasure
tables:
  - UnitOfMeasure
Entities: 
  - UnitOfMeasureEntity
AXPath: Organisation and administration\Setup\Units
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

`UnitOfMeasureEntity` Entity is allowed to operate with warehowses in D365FO.

## Key

- UnitSymbol

## Fields

| Field name                | Value example | Description |
| ------------------------- | ------------- | ----------- |
| (*)**UnitSymbol**         | "ea"          |             |
| IsFixedUnitSymbolAssigned | "No"          |             |
| SystemOfUnits             | "None"        |             |
| IsSystemUnit              | "No"          |             |
| FixedUnitSymbolAssignment | "Pieces"      |             |
| UnitClass                 | "Quantity"    |             |
| UnitDescription           | "Each"        |             |
| IsBaseUnit                | "Yes"         |             |
| DecimalPrecision          | 0             |             |
| NationalCode              | ""            |             |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/UnitsOfMeasure(UnitSymbol='ea')`

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
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#UnitsOfMeasure/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0MjExOTk7MCwyMjU2NTQyMTE5ODswLDA7MCw1NjM3MTQ0NTg1OzAsMCc=\"",
    "UnitSymbol": "ea",
    "IsFixedUnitSymbolAssigned": "No",
    "SystemOfUnits": "None",
    "IsSystemUnit": "No",
    "FixedUnitSymbolAssignment": "Pieces",
    "UnitClass": "Quantity",
    "UnitDescription": "Each",
    "IsBaseUnit": "Yes",
    "DecimalPrecision": 0,
    "NationalCode": ""
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/UnitsOfMeasure`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.UnitOfMeasure",
    "UnitSymbol": "bit"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://dev10plus15065719449a0027478devaos.cloudax.dynamics.com/data/$metadata#UnitsOfMeasure/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0Nzc2MTY7MCwwOzAsMDswLDA7MCwwJw==\"",
    "UnitSymbol": "bit",
    "IsFixedUnitSymbolAssigned": "No",
    "SystemOfUnits": "None",
    "IsSystemUnit": "No",
    "FixedUnitSymbolAssignment": "Pieces",
    "UnitClass": "Quantity",
    "UnitDescription": "",
    "IsBaseUnit": "No",
    "DecimalPrecision": 0,
    "NationalCode": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/UnitsOfMeasure(UnitSymbol='bit')`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.UnitOfMeasure",
    "DecimalPrecision": "3"
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

`DELETE : https://{{base_url}}/data/UnitsOfMeasure(UnitSymbol='bit')`

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
