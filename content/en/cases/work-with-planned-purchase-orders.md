---
title: "Works with planned purchase orders"
date: 2021-01-10
tags:
  - ReqPO
  - ReqTrans
  - InventDim
tables:
  - ReqPO
  - ReqTrans
  - InventDim
Entities: 
  - PlannedOrders
AXPath: Procurement and soursing\Purchase orders\Planned purchase orders
Operations:
  - Read
weight: 1
---

| Data entity AOT name  | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| --------------------- | ----------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| ReqPlannedOrderEntity | Planned orders    | PlannedOrders                  | Yes           | Yes         | Document | YES      |

`PlannedOrders` Entity is allowed to operate with planned purchase orders in D365FO.

__ENTITY IS READONLY!__

## Key

- dataAreaId
- RequirementPlanId
- PlannedOrderNumber

## Fields

| Field name                     | Value example             | Description |
| ------------------------------ | ------------------------- | ----------- |
| ProductDescription             | ""                        |             |
| AppendingTransferOrderNumber   | ""                        |             |
| ProductNumber                  | "D0005 : Default :  :  :" |             |
| ProductSizeId                  | ""                        |             |
| ItemNumber                     | "D0005"                   |             |
| ProductVersionId               | ""                        |             |
| RequirementPlanDescription     | "Long term plan"          |             |
| DeliveryDate                   | "2017-02-05T12:00:00Z"    |             |
| OrderTime                      | 25200,                    |             |
| SchedulingMethod               | "Rough"                   |             |
| ScheduledEndDate               | "2017-02-05T12:00:00Z"    |             |
| ScheduledStartDate             | "2017-02-05T12:00:00Z"    |             |
| PlannedOrderType               | "BOMPlannedOrder"         |             |
| ProductGroupId                 | "CarAudio"                |             |
| RequirementQuantity            | 319,                      |             |
| CostAmount                     | 63266.89,                 |             |
| VendorGroupId                  | ""                        |             |
| IsBulkOrder                    | "No"                      |             |
| PlanningFormulaItemNumber      | ""                        |             |
| PlannedOrderModifiedDateTime   | "2017-02-05T12:00:00Z"    |             |
| RequirementWarehouseId         | "41"                      |             |
| RequirementCatchWeightQuantity | 0,                        |             |
| YieldPercentage                | 0,                        |             |
| DeliveryTime                   | 55350,                    |             |
| VendorAccountNumber            | ""                        |             |
| ProductColorId                 | ""                        |             |
| IsDirectlyDerivedRequirement   | "No"                      |             |
| OrderDate                      | "2017-02-05T12:00:00Z"    |             |
| BOMId                          | "000024"                  |             |
| PurchaseQuantity               | 0,                        |             |
| PlannedOrderRouteOperationId   | "000027"                  |             |
| IsSequencedPlannedBatchOrder   | false,                    |             |
| RequirementDate                | "2017-02-05T12:00:00Z"    |             |
| ProductStyleId                 | ""                        |             |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/PlannedOrders(dataAreaId='usmf',RequirementPlanId='StaticPlan',PlannedOrderNumber='003855')`

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
    "@odata.context": "https://{{base_url}}/data/$metadata#PlannedOrders/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0MjEyMzcn\"",
    "dataAreaId": "usmf",
    "RequirementPlanId": "StaticPlan",
    "PlannedOrderNumber": "003855",
    "RequirementPlanType": "SchedPlan",
    "ProductSearchName": "",
    "BuyerGroupId": "",
    "IsLeadTimeUsingWorkingDays": "No",
    "LeadTimeDays": 0,
    "ProductConfigurationId": "Default",
    "ProcessingStatus": "Unadministered",
    "RequirementWarehouseLocationId": "",
    "AppendingPurchaseOrderNumber": "",
    "PurchaseUnitSymbol": "",
    "RequirementSiteId": "4",
    "ProductDescription": "",
    "AppendingTransferOrderNumber": "",
    "ProductNumber": "D0005 : Default :  :  :",
    "ProductSizeId": "",
    "ItemNumber": "D0005",
    "ProductVersionId": "",
    "RequirementPlanDescription": "Long term plan",
    "DeliveryDate": "2017-02-05T12:00:00Z",
    "OrderTime": 25200,
    "SchedulingMethod": "Rough",
    "ScheduledEndDate": "2017-02-05T12:00:00Z",
    "ScheduledStartDate": "2017-02-01T12:00:00Z",
    "PlannedOrderType": "BOMPlannedOrder",
    "ProductGroupId": "CarAudio",
    "RequirementQuantity": 319,
    "CostAmount": 63266.89,
    "VendorGroupId": "",
    "IsBulkOrder": "No",
    "PlanningFormulaItemNumber": "",
    "PlannedOrderModifiedDateTime": "2017-01-06T14:38:46Z",
    "RequirementWarehouseId": "41",
    "RequirementCatchWeightQuantity": 0,
    "YieldPercentage": 0,
    "DeliveryTime": 55350,
    "VendorAccountNumber": "",
    "ProductColorId": "",
    "IsDirectlyDerivedRequirement": "No",
    "OrderDate": "2017-02-01T12:00:00Z",
    "BOMId": "000024",
    "PurchaseQuantity": 0,
    "PlannedOrderRouteOperationId": "000027",
    "IsSequencedPlannedBatchOrder": false,
    "RequirementDate": "2017-02-05T12:00:00Z",
    "ProductStyleId": ""
}
```

</details>
