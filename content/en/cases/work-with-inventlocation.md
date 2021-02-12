---
title: "Work with inventory location (warehouse)"
date: 2021-01-10
tags:
  - InventLocation
tables:
  - InventLocation
Entities: 
  - Warehouses
AXPath: Warehouse management\Setup\Warehouse\Warehouses
Operations:
  - Read
  - Create
  - Update
  - Delete
weight: 1
---

| Data entity AOT name  | Entity name (DMF) | Public collection name (OData) | Support OData | Support DMF | Category | ReadOnly |
| --------------------- | ----------------- | ------------------------------ | ------------- | ----------- | -------- | -------- |
| InventWarehouseEntity | Warehouses        | Warehouses                     | Yes           | Yes         | Master   | No       |

`Warehouses` Entity is allowed to operate with warehowses in D365FO.

## Key

- dataAreaId
- WarehouseId

## Fields

| Field name                                              | Value example          | Description    |
| ------------------------------------------------------- | ---------------------- | -------------- |
| dataAreaId                                              | "usmf"                 | Company        |
| (*)__WarehouseId__                                      | "21"                   | WarehouseId    |
| PrimaryAddressLatitude                                  | 0                      |                |
| AreLaborStandardsAllowed                                | "No"                   |                |
| AreAdvancedWarehouseManagementProcessesEnabled          | "No"                   |                |
| WarehouseSpecificDefaultInventoryStatusId               | ""                     |                |
| ArePickingListsShipmentSpecificOnly                     | "No"                   |                |
| RawMaterialPickingInventoryIssueStatus                  | "Pick"                 |                |
| QuarantineWarehouseId                                   | "28"                   |                |
| InventoryCountingReasonCodePolicyName                   | ""                     |                |
| WillWarehouseLocationIdIncludeShelfIdByDefault          | "No"                   |                |
| ArePickingListsDeliveryModeSpecific                     | "No"                   |                |
| FormattedPrimaryAddress                                 | ""                     |                |
| WillManualLoadReleaseReserveInventory                   | "No"                   |                |
| WarehouseLocationIdBinIdFormat                          | ""                     |                |
| AreItemsCoveragePlannedManually                         | "No"                   |                |
| WillShippingCancellationDecrementLoadQuanity            | "No"                   |                |
| AutoUpdateShipmentRule                                  | "OnQuantityDecrease"   |                |
| PrimaryAddressStateId                                   | ""                     |                |
| WarehouseLocationIdRackIdFormat                         | ""                     |                |
| PrimaryAddressBuildingCompliment                        | ""                     |                |
| PrimaryAddressLocationSalesTaxGroupCode                 | ""                     |                |
| IsRefilledFromMainWarehouse                             | "No"                   |                |
| PrimaryAddressCountryRegionId                           | ""                     |                |
| WillWarehouseLocationIdIncludeRackIdByDefault           | "No"                   |                |
| RetailStoreQuantityAllocationReplenismentRuleWeight     | 0                      |                |
| IsPalletMovementDuringCycleCountingAllowed              | "No"                   |                |
| WarehouseLocationIdShelfIdFormat                        | ""                     |                |
| PrimaryAddressCountyId                                  | ""                     |                |
| MasterPlanningWorkCalendardId                           | ""                     |                |
| WarehouseWorkProcessingPolicyName                       | ""                     |                |
| ExternallyLocatedWarehouseVendorAccountNumber           | ""                     |                |
| MainRefillingWarehouseId                                | ""                     |                |
| WillAutomaticLoadReleaseReserveInventory                | "No"                   |                |
| IsPhysicalNegativeRetailStoreInventoryAllowed           | "No"                   |                |
| PrimaryAddressLocationRoles                             | ""                     |                |
| ExternallyLocatedWarehouseCustomerAccountNumber         | ""                     |                |
| PrimaryAddressDistrictName                              | ""                     |                |
| IsRetailStoreWarehouse                                  | "No"                   |                |
| IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled | "No"                   |                |
| WarehouseName                                           | "Site2-Dist.&Shipping" | Warehouse name |
| WillInventoryStatusChangeRemoveBlocking                 | "No"                   |                |
| PrimaryAddressStreet                                    | ""                     |                |
| DefaultContainerTypeId                                  | ""                     |                |
| IdentificationGroup                                     | "OwnStock"             |                |
| PrimaryAddressDescription                               | ""                     |                |
| WillProductionBOMsReserveWarehouseLevelOnly             | "No"                   |                |
| PrimaryAddressCity                                      | ""                     |                |
| PrimaryAddressStreetNumber                              | ""                     |                |
| PrimaryAddressStreetInKana                              | ""                     |                |
| PrimaryAddressZipCode                                   | ""                     |                |
| WillWarehouseLocationIdIncludeBinIdByDefault            | "No"                   |                |
| MaximumBatchPickingListQuantity                         | 0                      |                |
| AreWarehouseLocationCheckDigitsUnique                   | "No"                   |                |
| IsPrimaryAddressAssigned                                | "No"                   |                |
| ShouldWarehouseLocationIdIncludeAisleId                 | "No"                   |                |
| InventoryStatusChangeReservationRemovalLevel            | "None"                 |                |
| PrimaryAddressTimeZone                                  | null                   |                |
| TransitWarehouseId                                      | "29"                   |                |
| PrimaryAddressCityInKana                                | ""                     |                |
| WarehouseType                                           | "Standard"             |                |
| IsFinancialNegativeRetailStoreInventoryAllowed          | "No"                   |                |
| MaximumPickingListLineQuantity                          | 0                      |                |
| WarehouseReleaseReservationRequirementRule              | "NotApplicable"        |                |
| WillOrderReleasingConsolidateShipments                  | "No"                   |                |
| PrimaryAddressPostBox                                   | ""                     |                |
| PrimaryAddressLongitude                                 | 0                      |                |
| (*)__OperationalSiteId__                                | "2"                    | Warehouse site |
| IsFallbackWarehouse                                     | "Yes"                  |                |
| UnderdeliveryWarehouseId                                | ""                     |                |
| GoodsInTransitWarehouseId                               | ""                     |                |

## Postman

### Request for get data

`GET: https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='21')`

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
    "@odata.context": "{{base_url}}/data\$metadata#Warehouses/$entity",
    "@odata.etag": "W/\"JzAsMjI1NjU0MjE0MzA7MCwwOzAsNTYzNzE0NDgyOTswLDA7MCwwJw==\"",
    "dataAreaId": "usmf",
    "WarehouseId": "21",
    "PrimaryAddressLatitude": 0,
    "AreLaborStandardsAllowed": "No",
    "AreAdvancedWarehouseManagementProcessesEnabled": "No",
    "WarehouseSpecificDefaultInventoryStatusId": "",
    "ArePickingListsShipmentSpecificOnly": "No",
    "RawMaterialPickingInventoryIssueStatus": "Pick",
    "QuarantineWarehouseId": "28",
    "InventoryCountingReasonCodePolicyName": "",
    "WillWarehouseLocationIdIncludeShelfIdByDefault": "No",
    "ArePickingListsDeliveryModeSpecific": "No",
    "FormattedPrimaryAddress": "",
    "WillManualLoadReleaseReserveInventory": "No",
    "WarehouseLocationIdBinIdFormat": "",
    "AreItemsCoveragePlannedManually": "No",
    "WillShippingCancellationDecrementLoadQuanity": "No",
    "AutoUpdateShipmentRule": "OnQuantityDecrease",
    "PrimaryAddressStateId": "",
    "WarehouseLocationIdRackIdFormat": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "IsRefilledFromMainWarehouse": "No",
    "PrimaryAddressCountryRegionId": "",
    "WillWarehouseLocationIdIncludeRackIdByDefault": "No",
    "RetailStoreQuantityAllocationReplenismentRuleWeight": 0,
    "IsPalletMovementDuringCycleCountingAllowed": "No",
    "WarehouseLocationIdShelfIdFormat": "",
    "PrimaryAddressCountyId": "",
    "MasterPlanningWorkCalendardId": "",
    "WarehouseWorkProcessingPolicyName": "",
    "ExternallyLocatedWarehouseVendorAccountNumber": "",
    "MainRefillingWarehouseId": "",
    "WillAutomaticLoadReleaseReserveInventory": "No",
    "IsPhysicalNegativeRetailStoreInventoryAllowed": "No",
    "PrimaryAddressLocationRoles": "",
    "ExternallyLocatedWarehouseCustomerAccountNumber": "",
    "PrimaryAddressDistrictName": "",
    "IsRetailStoreWarehouse": "No",
    "IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled": "No",
    "WarehouseName": "Site 2 - Dist. & Shipping",
    "WillInventoryStatusChangeRemoveBlocking": "No",
    "PrimaryAddressStreet": "",
    "DefaultContainerTypeId": "",
    "IdentificationGroup": "OwnStock",
    "PrimaryAddressDescription": "",
    "WillProductionBOMsReserveWarehouseLevelOnly": "No",
    "PrimaryAddressCity": "",
    "PrimaryAddressStreetNumber": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressZipCode": "",
    "WillWarehouseLocationIdIncludeBinIdByDefault": "No",
    "MaximumBatchPickingListQuantity": 0,
    "AreWarehouseLocationCheckDigitsUnique": "No",
    "IsPrimaryAddressAssigned": "No",
    "ShouldWarehouseLocationIdIncludeAisleId": "No",
    "InventoryStatusChangeReservationRemovalLevel": "None",
    "PrimaryAddressTimeZone": null,
    "TransitWarehouseId": "29",
    "PrimaryAddressCityInKana": "",
    "WarehouseType": "Standard",
    "IsFinancialNegativeRetailStoreInventoryAllowed": "No",
    "MaximumPickingListLineQuantity": 0,
    "WarehouseReleaseReservationRequirementRule": "NotApplicable",
    "WillOrderReleasingConsolidateShipments": "No",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressLongitude": 0,
    "OperationalSiteId": "2",
    "IsFallbackWarehouse": "Yes",
    "UnderdeliveryWarehouseId": "",
    "GoodsInTransitWarehouseId": ""
}
```

</details>

### Request for create data

`POST : https://{{base_url}}/data/Warehouses`

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
    "@odata.type":"#Microsoft.Dynamics.DataEntities.Warehouse",
    "WarehouseId": "AAA-01",
    "OperationalSiteId": "2"
}
```

</details>

<details>
<summary>
Response:

</summary>

```json
{
    "@odata.context": "https://{{base_url}}/data/$metadata#Warehouses/$entity",
    "@odata.etag": "W/\"JzEsNjg3MTk0ODI4NzE7MSw2ODcxOTQ4Mjc5NDswLDA7MCwwOzAsMCc=\"",
    "dataAreaId": "usmf",
    "WarehouseId": "AAA-01",
    "PrimaryAddressLatitude": 0,
    "AreLaborStandardsAllowed": "No",
    "AreAdvancedWarehouseManagementProcessesEnabled": "No",
    "WarehouseSpecificDefaultInventoryStatusId": "",
    "ArePickingListsShipmentSpecificOnly": "No",
    "RawMaterialPickingInventoryIssueStatus": "Pick",
    "QuarantineWarehouseId": "",
    "InventoryCountingReasonCodePolicyName": "",
    "WillWarehouseLocationIdIncludeShelfIdByDefault": "No",
    "ArePickingListsDeliveryModeSpecific": "No",
    "FormattedPrimaryAddress": "",
    "WillManualLoadReleaseReserveInventory": "No",
    "WarehouseLocationIdBinIdFormat": "",
    "AreItemsCoveragePlannedManually": "No",
    "WillShippingCancellationDecrementLoadQuanity": "No",
    "AutoUpdateShipmentRule": "OnQuantityDecrease",
    "PrimaryAddressStateId": "",
    "WarehouseLocationIdRackIdFormat": "",
    "PrimaryAddressBuildingCompliment": "",
    "PrimaryAddressLocationSalesTaxGroupCode": "",
    "IsRefilledFromMainWarehouse": "No",
    "PrimaryAddressCountryRegionId": "",
    "WillWarehouseLocationIdIncludeRackIdByDefault": "No",
    "RetailStoreQuantityAllocationReplenismentRuleWeight": 0,
    "IsPalletMovementDuringCycleCountingAllowed": "No",
    "WarehouseLocationIdShelfIdFormat": "",
    "PrimaryAddressCountyId": "",
    "MasterPlanningWorkCalendardId": "",
    "WarehouseWorkProcessingPolicyName": "",
    "ExternallyLocatedWarehouseVendorAccountNumber": "",
    "MainRefillingWarehouseId": "",
    "WillAutomaticLoadReleaseReserveInventory": "No",
    "IsPhysicalNegativeRetailStoreInventoryAllowed": "No",
    "PrimaryAddressLocationRoles": "",
    "ExternallyLocatedWarehouseCustomerAccountNumber": "",
    "PrimaryAddressDistrictName": "",
    "IsRetailStoreWarehouse": "No",
    "IsBillOfLadingPrintingBeforeShipmentConfirmationEnabled": "No",
    "WarehouseName": "",
    "WillInventoryStatusChangeRemoveBlocking": "No",
    "PrimaryAddressStreet": "",
    "DefaultContainerTypeId": "",
    "IdentificationGroup": null,
    "PrimaryAddressDescription": "",
    "WillProductionBOMsReserveWarehouseLevelOnly": "No",
    "PrimaryAddressCity": "",
    "PrimaryAddressStreetNumber": "",
    "PrimaryAddressStreetInKana": "",
    "PrimaryAddressZipCode": "",
    "WillWarehouseLocationIdIncludeBinIdByDefault": "No",
    "MaximumBatchPickingListQuantity": 0,
    "AreWarehouseLocationCheckDigitsUnique": "No",
    "IsPrimaryAddressAssigned": "No",
    "ShouldWarehouseLocationIdIncludeAisleId": "No",
    "InventoryStatusChangeReservationRemovalLevel": "None",
    "PrimaryAddressTimeZone": null,
    "TransitWarehouseId": "",
    "PrimaryAddressCityInKana": "",
    "WarehouseType": "Standard",
    "IsFinancialNegativeRetailStoreInventoryAllowed": "No",
    "MaximumPickingListLineQuantity": 0,
    "WarehouseReleaseReservationRequirementRule": "NotApplicable",
    "WillOrderReleasingConsolidateShipments": "No",
    "PrimaryAddressPostBox": "",
    "PrimaryAddressLongitude": 0,
    "OperationalSiteId": "2",
    "IsFallbackWarehouse": "No",
    "UnderdeliveryWarehouseId": "",
    "GoodsInTransitWarehouseId": ""
}
```

</details>

### Request for update data

`PATCH : https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='AAA-01')`

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
    "@odata.type": "#Microsoft.Dynamics.DataEntities.Warehouse",
    "TransitWarehouseId": "29"
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

`DELETE : https://{{base_url}}/data/Warehouses(dataAreaId='usmf',WarehouseId='AAA-01')`

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
