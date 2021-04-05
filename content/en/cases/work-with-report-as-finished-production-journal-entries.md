---
title: "Work with Report As Finished Production Journal"
date: 2021-01-13
tags:
  - Report As Finished Production Journal
tables:
  - ProdJournalProd
Entities: 
  - ProdReportAsFinishedProductionJournalEntryEntity
AXPath: Production control\Production orders\All production orders\Views\Journals\Reported as finished
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

| Data entity AOT name                             | Entity name (DMF)                             | Public collection name (OData)           | Support OData | Support DMF | Category | ReadOnly |
| ------------------------------------------------ | --------------------------------------------- | ---------------------------------------- | ------------- | ----------- | -------- | -------- |
| ProdReportAsFinishedProductionJournalEntryEntity | Report as finished production journal entries | ReportAsFinishedProductionJournalEntries | Yes           | Yes         | Document | No       |

## Key

- JournalNumber
- JournalLineNumber

## Fields

| Field name                                              | Value example                | Description |
| ------------------------------------------------------- | ---------------------------- | ----------- |
| dataAreaId                                              | "usmf"                       |             |
| JournalNumber                                           | "00017"                      |             |
| JournalLineNumber                                       | 1                            |             |
| ProductConfigurationId                                  | ""                           |             |
| PostedDateTime                                          | "2016-08-15T08:22:26Z"       |             |
| ProductionType                                          | "BOM"                        |             |
| IsPosted                                                | "Yes"                        |             |
| ProductionSiteId                                        | "1"                          |             |
| ProductSizeId                                           | ""                           |             |
| ItemNumber                                              | "D0002"                      |             |
| JournalDescription                                      | "Report as finished Journal" |             |
| ItemSerialNumber                                        | ""                           |             |
| InventoryOwnerId                                        | ""                           |             |
| VoucherNumber                                           | "PRO-000014"                 |             |
| (*)**JournalName**                                      | "Finish"                     |             |
| ReportedGoodCatchWeightQuantity                         | 0                            |             |
| ReportedGoodInventoryQuantity                           | 200                          |             |
| ProductionPickingListJournalNumber                      | ""                           |             |
| ReceivedInventoryStatusId                               | ""                           |             |
| (*)**ProductionOrderNumber**                            | "P000001"                    |             |
| ReportedErrorCatchWeightQuantity                        | 0                            |             |
| (*)**InventoryLotId**                                   | "005881"                     |             |
| ItemBatchNumber                                         | ""                           |             |
| WarehouseId                                             | "11"                         |             |
| (*)**ReportAsFinishedDate**                             | "2016-08-15T12:00:00Z"       |             |
| WillAsFinishedPostingAcceptQuantityError                | "No"                         |             |
| IsReceiptReturned                                       | "No"                         |             |
| IsLastReportAsFinished                                  | "Yes"                        |             |
| ProductColorId                                          | ""                           |             |
| ErrorCause                                              | "None"                       |             |
| ReportedErrorInventoryQuantity                          | 0                            |             |
| LicensePlateNumber                                      | ""                           |             |
| WillReportAsFinishedPostingAutomaticallyPostPickingList | "No"                         |             |
| PostedUserId                                            | "KARL"                       |             |
| ProductStyleId                                          | ""                           |             |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/ReportAsFinishedProductionJournalEntries(dataAreaId='usmf',JournalNumber='00017',JournalLineNumber=1)`

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
    "@odata.context": "https://smartbusinessuat.sandbox.operations.dynamics.com/data/$metadata#ReportAsFinishedProductionJournalEntries/$entity",
    "@odata.etag": "W/\"JzAsNTYzNzE0NDU3Nic=\"",
    "dataAreaId": "usmf",
    "JournalNumber": "00017",
    "JournalLineNumber": 1,
    "ProductConfigurationId": "",
    "PostedDateTime": "2016-08-15T08:22:26Z",
    "ProductionType": "BOM",
    "IsPosted": "Yes",
    "ProductionSiteId": "1",
    "ProductSizeId": "",
    "ItemNumber": "D0002",
    "JournalDescription": "Report as finished Journal",
    "ItemSerialNumber": "",
    "InventoryOwnerId": "",
    "VoucherNumber": "PRO-000014",
    "JournalName": "Finish",
    "ReportedGoodCatchWeightQuantity": 0,
    "ReportedGoodInventoryQuantity": 200,
    "ProductionPickingListJournalNumber": "",
    "ReceivedInventoryStatusId": "",
    "ProductionOrderNumber": "P000001",
    "ReportedErrorCatchWeightQuantity": 0,
    "InventoryLotId": "005881",
    "ItemBatchNumber": "",
    "WarehouseId": "11",
    "ReportAsFinishedDate": "2016-08-15T12:00:00Z",
    "WillAsFinishedPostingAcceptQuantityError": "No",
    "IsReceiptReturned": "No",
    "IsLastReportAsFinished": "Yes",
    "ProductColorId": "",
    "ErrorCause": "None",
    "ReportedErrorInventoryQuantity": 0,
    "LicensePlateNumber": "",
    "WillReportAsFinishedPostingAutomaticallyPostPickingList": "No",
    "PostedUserId": "KARL",
    "ProductStyleId": ""
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/OperationalSites`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.ReportAsFinishedProductionJournalEntry",
    "ProductionOrderNumber": "P000164",
    "InventoryLotId": "011935",
    "ReportAsFinishedDate": "2020-08-15T12:00:00Z",
    "JournalName": "Finish"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://smartbusinessuat.sandbox.operations.dynamics.com/data/$metadata#ReportAsFinishedProductionJournalEntries/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0Nzg2NjMn\"",
    "dataAreaId": "usmf",
    "JournalNumber": "00935",
    "JournalLineNumber": 1,
    "ProductConfigurationId": "",
    "PostedDateTime": "1900-01-01T00:00:00Z",
    "ProductionType": "None",
    "IsPosted": "No",
    "ProductionSiteId": "",
    "ProductSizeId": "",
    "ItemNumber": "",
    "JournalDescription": "",
    "ItemSerialNumber": "",
    "InventoryOwnerId": "",
    "VoucherNumber": "",
    "JournalName": "Finish",
    "ReportedGoodCatchWeightQuantity": 0,
    "ReportedGoodInventoryQuantity": 0,
    "ProductionPickingListJournalNumber": "",
    "ReceivedInventoryStatusId": "",
    "ProductionOrderNumber": "P000164",
    "ReportedErrorCatchWeightQuantity": 0,
    "InventoryLotId": "011935",
    "ItemBatchNumber": "",
    "WarehouseId": "",
    "ReportAsFinishedDate": "2020-08-15T12:00:00Z",
    "WillAsFinishedPostingAcceptQuantityError": "No",
    "IsReceiptReturned": "No",
    "IsLastReportAsFinished": "No",
    "ProductColorId": "",
    "ErrorCause": "None",
    "ReportedErrorInventoryQuantity": 0,
    "LicensePlateNumber": "",
    "WillReportAsFinishedPostingAutomaticallyPostPickingList": "No",
    "PostedUserId": "",
    "ProductStyleId": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/ReportAsFinishedProductionJournalEntries(dataAreaId='usmf',JournalNumber='00935',JournalLineNumber=1)`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.ReportAsFinishedProductionJournalEntry",
    "JournalDescription": "Upd Report as finished Journal"
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

`DELETE : https://{{base_url}}/data/ReportAsFinishedProductionJournalEntries(dataAreaId='usmf',JournalNumber='00935',JournalLineNumber=1)`

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

### Related entityes

Related entity can be call as extension of base entity using key word $extend, or as separate call

- Warehouse
- ItemBatch
- ProductionSite
- ProductSize
- ProductColor
- ReleasedProductV2
- ProductStyle
- ProductionOrderHeader
