---
title: "Work with Production Order Headers"
date: 2021-01-13
tags:
  - Production orders
tables:
  - ProdTable
Entities: 
  - ProdProductionOrderHeaderEntity
AXPath: Production control\Production orders\All production orders\Views\Journals\Reported as finished
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

| Data entity AOT name            | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| ------------------------------- | ----------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| ProdProductionOrderHeaderEntity | Production orders | ProductionOrderHeaders         | Yes           | Yes         | Document | No       |

## Key

- dataAreaId
- ProductionOrderNumber

## Fields

| Field name                                     | Value example                | Description |
| ---------------------------------------------- | ---------------------------- | ----------- |
| @odata.etag                                    | "W/\"JzAsNTYzNzE0NDU3Nic=\"" |             |
| dataAreaId                                     | "usmf"                       |             |
| ProductionOrderNumber                          | "P000001"                    |             |
| ProductionOrderName                            | "Cabinet"                    |             |
| ScheduledEndDate                               | "2016-12-11T12:00:00Z"       |             |
| ProductionConsumptionWidthConversionFactor     | 0                            |             |
| ProductStyleId                                 | ""                           |             |
| SubcontractingPurchaseOrderNumber              | ""                           |             |
| SkipCreateProductionBOMLines                   | "Yes"                        |             |
| ProductionGroupId                              | ""                           |             |
| DeliveryTime                                   | 52200                        |             |
| ProductionOrderStatus                          | "Completed"                  |             |
| AutoReservationMode                            | "None"                       |             |
| DemandProductionOrderLineInventoryLotId        | ""                           |             |
| EndedDate                                      | "2016-08-15T12:00:00Z"       |             |
| SourceBOMVersionValidityDate                   | "2016-12-11T12:00:00Z"       |             |
| ProductionOrderRemainderStatus                 | "Completed"                  |             |
| ProductionOrderPriority                        | 0                            |             |
| DemandProductionOrderNumber                    | ""                           |             |
| InventoryStatusId                              | ""                           |             |
| (*)**ItemNumber**                              | "D0002"                      |             |
| ReportedAsFinishedDate                         | "2016-08-15T12:00:00Z"       |             |
| ProductionWarehouseId                          | "11"                         |             |
| ProductionSiteId                               | "1"                          |             |
| ProductSerialNumber                            | ""                           |             |
| ScheduledDate                                  | "2016-08-15T12:00:00Z"       |             |
| DemandTransferOrderNumber                      | ""                           |             |
| ProductSizeId                                  | ""                           |             |
| DemandSalesOrderNumber                         | ""                           |             |
| ProductionConsumptionDensityConversionFactor   | 0                            |             |
| DemandProductionOrderLineNumber                | ""                           |             |
| SubcontractingPurchaseOrderLineInventoryLotId  | ""                           |             |
| StartedDate                                    | "2016-08-15T12:00:00Z"       |             |
| DemandProductionOrderHeaderInventoryLotId      | ""                           |             |
| SchedulingMethod                               | "None"                       |             |
| ScheduledStartDate                             | "2016-11-28T12:00:00Z"       |             |
| DemandInventoryJournalLineInventoryLotId       | ""                           |             |
| ScheduledQuantity                              | 200                          |             |
| EstimatedDate                                  | "2016-08-15T12:00:00Z"       |             |
| WorkingTimeSchedulingPropertyId                | ""                           |             |
| ReleasedDate                                   | "1900-01-01T12:00:00Z"       |             |
| InventoryLotId                                 | "005881"                     |             |
| ProductionConsumptionHeightConversionFactor    | 0                            |             |
| SourcePlannedOrderNumber                       | "000001"                     |             |
| ProductConfigurationId                         | ""                           |             |
| LastSchedulingDate                             | "2016-12-11T12:00:00Z"       |             |
| StartedQuantity                                | 200                          |             |
| ProductionPoolId                               | ""                           |             |
| LicensePlateNumber                             | ""                           |             |
| ParentProductionOrderNumber                    | "P000001"                    |             |
| DemandTransferOrderLineReceivingInventoryLotId | ""                           |             |
| LastSchedulingTime                             | 55800                        |             |
| ProductVersionId                               | ""                           |             |
| EstimatedQuantity                              | 200                          |             |
| SourceBOMId                                    | "D0002BOM"                   |             |
| ProductionWarehouseLocationId                  | ""                           |             |
| DemandSalesOrderLineInventoryLotId             | ""                           |             |
| IsProductionOrderSchedulingLocked              | "No"                         |             |
| SourceMasterPlanId                             | "StaticPlan"                 |             |
| ProductionOrderLedgerPostingRule               | "ItemCategory"               |             |
| ProductionOrderProfitSettingMethod             | "Standard"                   |             |
| LastSchedulingDateDirection                    | "Backward"                   |             |
| ItemBatchNumber                                | ""                           |             |
| IsProductionRouteOperationValid                | "No"                         |             |
| ProductColorId                                 | ""                           |             |
| RemainingReportAsFinishedQuantity              | 0                            |             |
| SourceRouteId                                  | "000004"                     |             |
| AreRouteJobsGenerated                          | "No"                         |             |
| WarehouseReleaseReservationRequirementRule     | "AllowPartialReservation"    |             |
| ScheduledStartTime                             | 55800                        |             |
| DeliveryDate                                   | "2016-12-11T12:00:00Z"       |             |
| ScheduledEndTime                               | 55800                        |             |
| ProductionLevel                                | 0                            |             |
| DefaultLedgerDimensionDisplayValue             | "001--"                      |             |
| GanttChartColorNumber                          | 128                          |             |
| ProductionConsumptionDepthConversionFactor     | 0                            |             |
| DemandInventoryJournalNumber                   | ""                           |             |
| SkipCreateProductionRouteOperations            | "Yes"                        |             |
| InventoryOwnerId                               | ""                           |             |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/ProductionOrderHeaders(dataAreaId='usmf',ProductionOrderNumber='P000164')`

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
    "@odata.context": "https://smartbusinessuat.sandbox.operations.dynamics.com/data/$metadata#ProductionOrderHeaders/$entity",
    "@odata.etag": "W/\"JzAsMzU2MzcxNjExMTEn\"",
    "dataAreaId": "usmf",
    "ProductionOrderNumber": "P000164",
    "ProductionOrderName": "Ruggedized Laser Projector",
    "ScheduledEndDate": "2017-01-20T12:00:00Z",
    "ProductionConsumptionWidthConversionFactor": 0,
    "ProductStyleId": "",
    "SubcontractingPurchaseOrderNumber": "",
    "SkipCreateProductionBOMLines": "Yes",
    "ProductionGroupId": "",
    "DeliveryTime": 36000,
    "ProductionOrderStatus": "StartedUp",
    "AutoReservationMode": "None",
    "DemandProductionOrderLineInventoryLotId": "",
    "EndedDate": "1900-01-01T12:00:00Z",
    "SourceBOMVersionValidityDate": "2017-01-20T12:00:00Z",
    "ProductionOrderRemainderStatus": "Route",
    "ProductionOrderPriority": 0,
    "DemandProductionOrderNumber": "",
    "InventoryStatusId": "",
    "ItemNumber": "D0111",
    "ReportedAsFinishedDate": "1900-01-01T12:00:00Z",
    "ProductionWarehouseId": "11",
    "ProductionSiteId": "1",
    "ProductSerialNumber": "",
    "ScheduledDate": "2017-01-18T12:00:00Z",
    "DemandTransferOrderNumber": "",
    "ProductSizeId": "",
    "DemandSalesOrderNumber": "000754",
    "ProductionConsumptionDensityConversionFactor": 0,
    "DemandProductionOrderLineNumber": "",
    "SubcontractingPurchaseOrderLineInventoryLotId": "",
    "StartedDate": "2017-01-18T12:00:00Z",
    "DemandProductionOrderHeaderInventoryLotId": "",
    "SchedulingMethod": "JobScheduled",
    "ScheduledStartDate": "2017-01-20T12:00:00Z",
    "DemandInventoryJournalLineInventoryLotId": "",
    "ScheduledQuantity": 3,
    "EstimatedDate": "2017-01-18T12:00:00Z",
    "WorkingTimeSchedulingPropertyId": "",
    "ReleasedDate": "1900-01-01T12:00:00Z",
    "InventoryLotId": "011935",
    "ProductionConsumptionHeightConversionFactor": 0,
    "SourcePlannedOrderNumber": "003281",
    "ProductConfigurationId": "",
    "LastSchedulingDate": "2017-01-20T12:00:00Z",
    "StartedQuantity": 3,
    "ProductionPoolId": "",
    "LicensePlateNumber": "",
    "ParentProductionOrderNumber": "P000164",
    "DemandTransferOrderLineReceivingInventoryLotId": "",
    "LastSchedulingTime": 36000,
    "ProductVersionId": "",
    "EstimatedQuantity": 3,
    "SourceBOMId": "000115",
    "ProductionWarehouseLocationId": "",
    "DemandSalesOrderLineInventoryLotId": "011925",
    "IsProductionOrderSchedulingLocked": "No",
    "SourceMasterPlanId": "DynPlan",
    "ProductionOrderLedgerPostingRule": "ItemCategory",
    "ProductionOrderProfitSettingMethod": "Standard",
    "LastSchedulingDateDirection": "Backward",
    "ItemBatchNumber": "140127-000003",
    "IsProductionRouteOperationValid": "No",
    "ProductColorId": "",
    "RemainingReportAsFinishedQuantity": 0,
    "SourceRouteId": "000091",
    "AreRouteJobsGenerated": "Yes",
    "WarehouseReleaseReservationRequirementRule": "AllowPartialReservation",
    "ScheduledStartTime": 34380,
    "DeliveryDate": "2017-01-20T12:00:00Z",
    "ScheduledEndTime": 36000,
    "ProductionLevel": 0,
    "DefaultLedgerDimensionDisplayValue": "001--",
    "GanttChartColorNumber": 128,
    "ProductionConsumptionDepthConversionFactor": 0,
    "DemandInventoryJournalNumber": "",
    "SkipCreateProductionRouteOperations": "Yes",
    "InventoryOwnerId": ""
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/ProductionOrderHeaders

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.ProductionOrderHeader",
    "ItemNumber": "D0111"
}
```

</details>

<details>
    <summary>
    Response:
    </summary>

```json
{
    "@odata.context": "https://smartbusinessuat.sandbox.operations.dynamics.com/data/$metadata#ProductionOrderHeaders/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0ODAwNjcn\"",
    "dataAreaId": "usmf",
    "ProductionOrderNumber": "P000211",
    "ProductionOrderName": "Ruggedized Laser Projector",
    "ScheduledEndDate": "1900-01-01T12:00:00Z",
    "ProductionConsumptionWidthConversionFactor": 0,
    "ProductStyleId": "",
    "SubcontractingPurchaseOrderNumber": "",
    "SkipCreateProductionBOMLines": "Yes",
    "ProductionGroupId": "",
    "DeliveryTime": 36000,
    "ProductionOrderStatus": "Created",
    "AutoReservationMode": "Estimation",
    "DemandProductionOrderLineInventoryLotId": "",
    "EndedDate": "1900-01-01T12:00:00Z",
    "SourceBOMVersionValidityDate": "2021-04-05T12:00:00Z",
    "ProductionOrderRemainderStatus": "None",
    "ProductionOrderPriority": 0,
    "DemandProductionOrderNumber": "",
    "InventoryStatusId": "",
    "ItemNumber": "D0111",
    "ReportedAsFinishedDate": "1900-01-01T12:00:00Z",
    "ProductionWarehouseId": "11",
    "ProductionSiteId": "1",
    "ProductSerialNumber": "",
    "ScheduledDate": "1900-01-01T12:00:00Z",
    "DemandTransferOrderNumber": "",
    "ProductSizeId": "",
    "DemandSalesOrderNumber": "",
    "ProductionConsumptionDensityConversionFactor": 0,
    "DemandProductionOrderLineNumber": "",
    "SubcontractingPurchaseOrderLineInventoryLotId": "",
    "StartedDate": "1900-01-01T12:00:00Z",
    "DemandProductionOrderHeaderInventoryLotId": "",
    "SchedulingMethod": "None",
    "ScheduledStartDate": "1900-01-01T12:00:00Z",
    "DemandInventoryJournalLineInventoryLotId": "",
    "ScheduledQuantity": 1,
    "EstimatedDate": "1900-01-01T12:00:00Z",
    "WorkingTimeSchedulingPropertyId": "",
    "ReleasedDate": "1900-01-01T12:00:00Z",
    "InventoryLotId": "012641",
    "ProductionConsumptionHeightConversionFactor": 0,
    "SourcePlannedOrderNumber": "",
    "ProductConfigurationId": "",
    "LastSchedulingDate": "1900-01-01T12:00:00Z",
    "StartedQuantity": 0,
    "ProductionPoolId": "",
    "LicensePlateNumber": "",
    "ParentProductionOrderNumber": "P000211",
    "DemandTransferOrderLineReceivingInventoryLotId": "",
    "LastSchedulingTime": 0,
    "ProductVersionId": "",
    "EstimatedQuantity": 0,
    "SourceBOMId": "000115",
    "ProductionWarehouseLocationId": "",
    "DemandSalesOrderLineInventoryLotId": "",
    "IsProductionOrderSchedulingLocked": "No",
    "SourceMasterPlanId": "",
    "ProductionOrderLedgerPostingRule": "ItemCategory",
    "ProductionOrderProfitSettingMethod": "Standard",
    "LastSchedulingDateDirection": "None",
    "ItemBatchNumber": "210405-000031",
    "IsProductionRouteOperationValid": "No",
    "ProductColorId": "",
    "RemainingReportAsFinishedQuantity": 1,
    "SourceRouteId": "000091",
    "AreRouteJobsGenerated": "No",
    "WarehouseReleaseReservationRequirementRule": "AllowPartialReservation",
    "ScheduledStartTime": 0,
    "DeliveryDate": "2021-04-05T12:00:00Z",
    "ScheduledEndTime": 0,
    "ProductionLevel": 0,
    "DefaultLedgerDimensionDisplayValue": "",
    "GanttChartColorNumber": 128,
    "ProductionConsumptionDepthConversionFactor": 0,
    "DemandInventoryJournalNumber": "",
    "SkipCreateProductionRouteOperations": "Yes",
    "InventoryOwnerId": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/ProductionOrderHeaders(dataAreaId='usmf',ProductionOrderNumber='P000211')`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.ProductionOrderHeader",
    "ScheduledQuantity": 10
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

`DELETE : https://{{base_url}}/data/ProductionOrderHeaders(dataAreaId='usmf',ProductionOrderNumber='P000211')`

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

- ProdutionOrderBOMLines
- ReportAsFinishedProductionJournalEntries
- ProdutionOrderRouteOperations
- DimensionSet
- JobCardProductionJournalEntries
- QualityOrderHeaders
- RouteCardProductionJournalEntries
- ProductionPickingListJournalEntries